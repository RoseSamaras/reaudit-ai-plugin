---
name: project-onboarding
description: Create a Reaudit project and run the full onboarding pipeline — website crawl, AI brand analysis, SEO audit, competitor detection, and prompt suggestions — then turn the results into a working visibility-tracking setup. Use when a user wants to add a new brand, client, or website to Reaudit, or asks to "set up" a project end-to-end.
---

# Project Onboarding

Take a brand from "just a website URL" to a fully tracked Reaudit project in one flow.

## When to Use

- User wants to add a new brand, client, or market to Reaudit
- User says "set up my site", "onboard this client", or "create a project for X"
- An agency user is spinning up a prospect/teaser audit for a pitch
- User wants the initial SEO + AI-readiness picture for a site they don't track yet

## Instructions

### Step 1: Gather the required inputs

`create_project` requires all four:

- **name** — the brand/project name (e.g. "Aurora Skincare UK")
- **website** — the URL to crawl (e.g. https://example.com)
- **defaultLocation** — the tracked market's country code (e.g. GB, US, DE)
- **language** — the language for prompts and content (e.g. en, de, el)

If the user gave only a URL, ask for (or infer) the market and language before calling.

### Step 2: Create the project

- Call `create_project`. It runs the full onboarding pipeline: website crawl, AI brand analysis, SEO audit, competitor detection, and AI-prompt suggestions.
- It is **long-running (1-3 minutes)**. If the call times out or errors, do **not** call it again — the job may have completed server-side. Check `list_projects` for the new project and `list_audits` for its audit.
- Project creation counts against the plan's project limit; `get_usage_summary` shows the remaining quota.

### Step 3: Read the onboarding results

The response includes `projectId`, `auditId`, current + potential SEO scores, detected industry, competitors, suggested prompts, and top recommendations. For the full audit, use `get_audit_details` with the returned `auditId`.

### Step 4: Turn suggestions into tracking

- Create a prompt topic from the suggested prompts with `create_prompt_topic` (or `track_prompt` for one-offs)
- Add any competitors from the brief that detection missed via `update_project_settings`
- Set brand aliases and products in settings so mention-matching is accurate

### Step 5: Round out the baseline

- `check_crawlability` (free) — confirm AI bots can reach the site
- `scan_agent_readiness` (free) — agentic-era readiness level 0-5
- `get_visibility_score` after the first tracking run — the baseline number

## Best Practices

- One project = one brand in one market. A second market (e.g. same brand, US) is a second project.
- Never retry `create_project` blindly after an error — check `list_projects` first to avoid duplicates and double-charged onboarding.
- Present the onboarding output as a baseline story: SEO score today → potential score, plus the suggested prompts as the tracking plan.
