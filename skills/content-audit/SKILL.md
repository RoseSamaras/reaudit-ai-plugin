---
name: content-audit
description: Audit a project's existing content for AI search visibility (GEO) and draft grounded fixes. Use when a user wants to check whether their existing pages are fresh, readable, entity-rich, on-brand, and extractable by AI engines — and to fix the ones that are not. Covers building a content inventory, running the audit, triaging findings by severity, and generating fixes.
---

# Content Audit for AI Search Visibility

Continuously assess the content a brand already has and make it more
discoverable and citable by AI search engines (ChatGPT, Claude, Perplexity,
Gemini). This complements content generation: generation creates new pages,
auditing keeps the existing library competitive.

## When to Use

- User wants to know which existing pages are weak for AI search
- User asks about stale content, thin content, or pages AI "can't read"
- User wants a recurring health check across their whole site or a CMS
- User wants concrete, page-level fixes rather than generic advice

## Instructions

### Step 0: Establish Context

- Use `set_active_project` (or pass `projectId`) to set the project context
- Use `get_project_settings` to confirm the brand, products, and writing
  style. The brand-voice check only runs when a writing style / tone of voice
  is configured — if it's empty, skip `voice_drift` to avoid wasted credits.

### Step 1: Build the Content Inventory

- Use `import_content_inventory` to populate the auditable inventory.
  - `source`: `all` (default), `reaudit`, `wordpress`, `shopify`, or `sitemap`
- Run this before auditing. If nothing imports, the project likely has no
  connected source or sitemap — tell the user how to connect one.

### Step 2: Run the Audit

- Use `run_content_audit` with the project context.
  - `checks`: any of `geo_shape`, `freshness`, `readability`, `entity_gap`,
    `voice_drift`. Defaults to `geo_shape`, `freshness`, `readability`.
  - `source`: limit to one inventory source (optional)
  - `limit`: cap the number of pages (1-500, default 200)
- This is long-running (1-3 min). The server keeps the call alive and reports a
  severity summary plus credits used when it finishes.
- If the call is cut off, DO NOT re-run it — call
  `list_content_audit_findings` (omit `runId`) to read the latest completed run.

### Step 3: Triage the Findings

- Use `list_content_audit_findings` (defaults to the latest completed run).
  - Filter with `severity` (`critical` / `high` / `medium` / `low`) or `check`.
- Prioritize critical and high findings. Each finding has the page URL, the
  check, a specific issue message, a recommendation, and a Finding ID.

### Step 4: Generate Fixes

- Use `generate_content_fix` with a Finding ID to draft a grounded fix.
  - For Reaudit-managed pages, it saves a full rewrite to the Content Factory.
  - For external pages, it returns a copyable suggestion to apply in the CMS.
- Fix generation uses LLM credits; generate fixes for the findings that matter
  most rather than every low-severity item.

## What the Checks Mean

- **geo_shape** — Does the page lead with a direct answer, use clear/question
  headings, and is it structured so AI engines can extract and cite it?
- **freshness** — Is the content stale based on its last-modified date?
- **readability** — Is the reading grade level and sentence complexity friendly
  to both readers and AI extraction?
- **entity_gap** — Does the page actually name the brand, products, and core
  topics AI engines rely on when recommending?
- **voice_drift** — Does the page match the configured brand voice? (LLM-based)

## Best Practices

- Always import the inventory before the first audit.
- Start with the free structural checks; add `voice_drift` only when a brand
  voice is configured.
- Schedule recurring audits so freshness and drift are caught early.
- Fix high-severity, high-traffic pages first; re-run the audit to confirm the
  score improved.
