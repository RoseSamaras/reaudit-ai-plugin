---
name: shopping
description: Track Google Merchant Center Shopping AI visibility, competitive share, and product feed health
argument-hint: [project or metric]
---

# Shopping AI Visibility

Use the Reaudit MCP tools to see how your products surface in AI-driven
Shopping experiences via your connected Google Merchant Center account:

1. For Shopping visibility, use `get_shopping_visibility` with a `projectId`

`get_shopping_visibility` returns:

- **Your visibility** — relative Shopping visibility on organic surfaces
- **Share of voice** — competitive visibility vs tracked competitor domains
- **Organic Shopping funnel** — impressions, clicks, and CTR
- **Attribute completeness** — how well your feed describes products so AI
  systems can understand and recommend them (color, material, gtin, etc.)
- **Top feed issues** — critical/error/suggestion problems that make products
  hard for AI to recommend, with affected product counts

## Requirements

- A Google Merchant Center account connected from
  **Dashboard > AI Commerce** (or **Analytics > AI Commerce**)
- At least one synced Shopping snapshot (syncs run hourly; the first sync
  populates the data)

## Example prompts

- "How visible are my products in Shopping?"
- "What's my Shopping share of voice vs competitors?"
- "Which product attributes are incomplete in my feed?"
- "What feed issues are hurting how AI recommends my products?"
- "Show my organic Shopping funnel — impressions, clicks, CTR"
