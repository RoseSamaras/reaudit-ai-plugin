---
name: github
description: Open pull requests that fix the SEO and GEO issues found in your audits
argument-hint: [recommendation id, audit id, or recipe id]
---

# GitHub Auto-Fixes

Use the Reaudit MCP tools to turn audit findings into pull requests on the
project's connected repository:

1. Use `list_repo_connections` to confirm the active project has a GitHub
   repo connected. If it does not, point the user at
   **Dashboard > Tools > GitHub** to install the Reaudit GitHub App.
2. Use `propose_seo_fixes` for a dry-run preview of the patch that would be
   produced for a single recommendation, an entire audit, or a specific
   recipe id.
3. Use `open_seo_fix_pr` to write the fix and open a pull request on a fresh
   branch with a description that links back to the audit recommendation.

Reaudit never pushes to the default branch. Every change is a pull request
the user reviews and merges in their repo.

## Example prompts

- "Which of my projects has a GitHub repo connected?"
- "Preview the fixes you would open for my latest audit"
- "Open a PR that fixes the missing llms.txt recommendation"
- "Open one PR that batches every applicable fix from audit 9F2C..."
- "Show me the open Reaudit pull requests on this project"
