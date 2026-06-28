---
name: content-audit
description: Audit existing content for AI search visibility and fix the gaps
argument-hint: [project or "run an audit"]
---

# Content Audit

Use the Reaudit MCP tools to continuously audit the user's existing content for
AI search visibility (GEO) and draft grounded fixes:

1. Build the inventory first with `import_content_inventory` (source: `all`,
   `reaudit`, `wordpress`, `shopify`, or `sitemap`). Run this before auditing so
   there are pages to score.
2. Run the audit with `run_content_audit`. Pass `checks` to choose what to score
   and `source` / `limit` to scope it. This is long-running (1-3 min) — the
   server keeps the call alive.
3. Read the issues with `list_content_audit_findings` (omit `runId` to use the
   latest completed run). Triage by `severity` or `check`.
4. Draft a fix for any finding with `generate_content_fix` using its Finding ID.

## The five checks

- `geo_shape` — answer-shape / extractability for AI engines (answer-first lead,
  clear headings, structure)
- `freshness` — how stale the page is
- `readability` — reading grade level and sentence complexity
- `entity_gap` — whether the page actually names the brand, products, and core
  topics AI engines rely on
- `voice_drift` — brand-voice consistency (uses LLM credits; needs a brand voice
  configured in project settings)

Defaults to `geo_shape`, `freshness`, `readability` when `checks` is omitted.

## Notes

- The structural checks are free; only `voice_drift` and `generate_content_fix`
  use LLM credits. The run summary reports credits used.
- For Reaudit-managed pages, the fix is a full rewrite saved to the Content
  Factory; for external pages it's a copyable suggestion.

## Example prompts

- "Audit my existing content for AI search visibility"
- "Import my sitemap and run a content audit on the 50 newest pages"
- "Which of my pages are stale or hard for AI to cite?"
- "Show me the high-severity findings from the last audit"
- "Generate a fix for the lowest-scoring page"
