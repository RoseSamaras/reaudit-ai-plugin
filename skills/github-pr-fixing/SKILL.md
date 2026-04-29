---
name: github-pr-fixing
description: Fix SEO and GEO issues by opening pull requests in the user's repo. Use when the user wants to fix audit findings in code, open a PR for an SEO recommendation, or batch-fix every applicable issue from a recent audit.
---

# GitHub PR Fixing

Turn Reaudit audit findings into pull requests on the user's connected
GitHub repository. The user reviews and merges the PR. Reaudit never pushes
directly to the default branch.

## When to Use

- User asks to fix SEO or GEO issues in code
- User asks to "open a PR" or "open a pull request" for a recommendation
- User mentions a specific audit recommendation and asks for the fix
- User asks to batch every applicable fix from an audit into one PR

## Instructions

### Step 0: Establish Project Context

- Use `list_projects` to show available projects
- Use `set_active_project` with the chosen project ID

### Step 1: Confirm a Repo Is Connected

- Use `list_repo_connections` to verify the active project has a GitHub
  repository linked
- If no repo is connected, ask the user to install the Reaudit GitHub App
  from **Dashboard > Tools > GitHub** and stop. Do not attempt to call
  `propose_seo_fixes` or `open_seo_fix_pr` without a connection.

### Step 2: Identify the Target Recommendation or Audit

- If the user named a specific recommendation, use that
- If the user wants "everything from the latest audit", use `get_latest_audit`
  (or the audit tool the user references) to fetch the audit id
- For ambiguous requests, list the top recommendations from the latest
  audit and ask the user to pick one or confirm "all of them"

### Step 3: Preview With propose_seo_fixes

- Use `propose_seo_fixes` to do a dry-run. This returns the list of files
  that would change and a short summary per recipe.
- Show the user the preview before opening the PR. Do not skip this step
  on first use.

### Step 4: Open the Pull Request

- Use `open_seo_fix_pr` once the user confirms.
- Pass the same recommendation id, audit id, or recipe ids you previewed.
- Return the PR URL, branch name, and the list of files changed.

### Step 5: Hand Off

- Tell the user the PR is ready for review and link it.
- Suggest re-running the audit after merge to confirm the fix landed.

## Best Practices

- Always preview with `propose_seo_fixes` before calling `open_seo_fix_pr`.
- Never invent recipe ids. Pull them from the propose preview or the audit
  recommendation payload.
- If `open_seo_fix_pr` reports "no fixes applied", explain that the repo is
  already compliant for that recommendation and do not retry.
- Respect the user's branch naming conventions if they ask, otherwise let
  Reaudit pick a `reaudit/` prefixed branch.
- Never push to the default branch. Every fix is a PR.
