---
name: shopping-visibility
description: Analyze Google Merchant Center Shopping AI visibility — competitive share of voice, the organic Shopping funnel, product attribute completeness, and the feed issues that make products hard for AI to recommend. Use when the user asks about Shopping visibility, AI Commerce, Merchant Center, product feed health, or how their products surface in AI shopping experiences.
---

# Shopping AI Visibility

Show the user how their products surface in AI-driven Shopping experiences
using data synced from their connected Google Merchant Center account. This
is the "AI Commerce" view: the question shifts from "what position do I rank?"
to "does AI understand my products well enough to recommend them?"

## When to Use

- User asks how visible their products are in Shopping / AI shopping
- User asks about Merchant Center, AI Commerce, or product feed health
- User wants competitive Shopping share of voice
- User asks why their products aren't being recommended by AI
- User wants to find incomplete or missing product attributes

## Instructions

### Step 0: Establish Project Context

- Use `list_projects` to show available projects
- Use `set_active_project` with the chosen project ID

### Step 1: Pull Shopping Visibility

- Use `get_shopping_visibility` with the active `projectId`.
- If the response says Merchant Center is not connected, tell the user to
  connect it from **Dashboard > AI Commerce** (also reachable under the
  **Analytics** section) and stop — there is nothing to analyze yet.
- If it says no snapshot has synced yet, explain that syncs run hourly and
  the first sync populates the data; suggest triggering a sync from the
  AI Commerce dashboard.

### Step 2: Summarize the Headline Metrics

- Lead with the user's own visibility and product count.
- Report the organic Shopping funnel: impressions, clicks, CTR.

### Step 3: Frame the Competitive Picture

- Walk through share of voice vs competitor domains, highest first.
- Call out where competitors out-rank the user and by how much.

### Step 4: Diagnose Feed Quality

- Surface attribute completeness — which attributes are well covered and
  which are sparse. Sparse high-value attributes (gtin, color, material,
  size) are the biggest "AI can't understand my product" risks.
- List the top feed issues, ordered critical → error → suggestion, with the
  number of products affected.

### Step 5: Recommend Next Actions

- Translate the gaps into concrete fixes: fill missing attributes, resolve
  critical/error issues first, then suggestions.
- Point the user to the full AI Commerce dashboard for per-product detail.

## Best Practices

- Always confirm a Merchant Center connection before analyzing — never
  fabricate Shopping numbers.
- Prioritize critical and error feed issues over suggestions; they block
  products from being shown at all.
- Treat low completeness on high-value attributes as the root cause of weak
  AI recommendations, not a cosmetic issue.
- The AI Shopping Performance Insights block is reserved for when Google
  ships it via the Merchant API — until then, do not invent AI share-of-voice
  numbers; report what the organic Shopping data shows.
