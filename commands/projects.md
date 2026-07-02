---
name: projects
description: Create and manage Reaudit projects — full onboarding (crawl, AI brand analysis, SEO audit, competitor detection, prompt suggestions) from a single command
argument-hint: [website or project name]
---

# Projects

Use the Reaudit MCP tools to help the user create and manage projects:

1. Use `list_projects` to see existing projects and their IDs
2. To create a new project, use `create_project` with `name`, `website`, `defaultLocation` (country code, e.g. GB, US), and `language` (e.g. en) — it runs the **full onboarding pipeline**: website crawl, AI brand analysis, SEO audit, competitor detection, and AI-prompt suggestions. It is long-running (1-3 min); do not re-call it if the response is slow — check `list_projects` / `list_audits` instead
3. The result includes the new `projectId`, `auditId`, SEO scores (current + potential), detected industry, competitors, and suggested prompts
4. Follow up with `create_prompt_topic` / `track_prompt` to start tracking the suggested prompts
5. Use `get_project_settings` / `update_project_settings` to configure brand aliases, products, and competitors
6. Use `get_usage_summary` to check how many projects the current plan allows

## Example prompts

- "Create a new project for my client's site https://example.com, UK market, English"
- "Set up Aurora Skincare on Reaudit and start tracking the suggested prompts"
- "List my projects"
- "What did onboarding find for the new project? Show the audit scores and competitors"
- "Add these competitors to the project settings"
