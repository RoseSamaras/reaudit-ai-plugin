---
name: chatgpt-competitor-ads
description: Adthena-style intelligence for ChatGPT Search sponsored carousel ads. Use when a user wants to know which advertisers dominate ChatGPT for their queries, how often sponsored cards appear, or what changed in competitor advertising on ChatGPT this week.
---

# ChatGPT Competitor Ad Intelligence

Surface Adthena-style competitor advertising intelligence from the sponsored
carousel cards that appear on ChatGPT Search alongside the organic answer.
Every tracked-prompt run captures the carousel; these tools aggregate it.

## When to Use

- User asks "who is advertising on ChatGPT for my queries?"
- User asks how often sponsored cards appear in ChatGPT responses to their tracked prompts
- User asks for a competitor advertising weekly diff or "what changed"
- User mentions Adthena, paid search intelligence, or competitor ad monitoring
- User wants to see ad-presence rate, top advertisers, or new/lost advertiser movements

## Instructions

### Step 0: Establish Context

- Use `set_active_project` to set the project
- Confirm the project has tracked prompts. Competitor ad data is only
  collected on prompt runs after **2026-05-08** (v1.11.0 of the MCP) — older
  prompts will show empty data until they next run.

### Step 1: Get the Overview

- Use `get_chatgpt_competitor_ad_summary` to get:
  - **Ad-presence rate** — % of tracked prompts that surfaced at least one sponsored card
  - **Total carousel cards** — raw card volume across the lookback window
  - **Unique advertisers** — distinct advertisers seen
  - **Own / Competitor / Other split** — share of cards attributed to the
    user's brand, tracked competitors, or unidentified advertisers
- Default lookback is 30 days; pass `days` (1–90) to widen or narrow

### Step 2: Identify Who's Dominating

- Use `get_chatgpt_top_advertisers` with optional `days` and `limit` (1–100,
  default 20)
- Each entry returns: advertiser name, card count, presence rate across the
  user's tracked prompts, and a tag of **own brand**, **tracked competitor**,
  or **other**
- Surface the top tracked competitors first — those are the ones the user
  cares about most
- For untagged "other" advertisers that appear with high frequency, suggest
  adding them as tracked competitors via `add_competitor` so future weeks
  attribute their movements correctly

### Step 3: Surface Weekly Movement

- Use `get_chatgpt_competitor_ad_changes` for the "what changed this week"
  diff (last 7 days vs. prior 7 days):
  - **New advertisers** — advertisers seen this week that weren't seen the
    week prior
  - **Lost advertisers** — advertisers gone from sponsored cards this week
  - **Presence-rate shifts** — advertisers whose presence rate moved
    meaningfully week over week
- This is the highest-signal view for an executive weekly review

### Step 4: Recommend Action

Based on the data, suggest one of:

- **Gap to fill** — if a tracked competitor's presence rate jumped and the
  user's own brand has no ChatGPT Ads campaign yet, point to
  `/reaudit:chatgpt-ads` and `generate_ad_creative` with
  `platform: 'openai'`, `format: 'chat_card'`
- **Track an untagged dominant advertiser** — use `add_competitor` if a
  high-volume "other" advertiser is in the user's space
- **No action** — if the diff is noise (low total carousel volume, no
  meaningful shifts), say so clearly. The strongest signal is sometimes
  "nothing happened this week."

## Best Practices

- **Forward-only collection.** Carousel data started accumulating on
  2026-05-08 (v1.11.0). Don't promise historical backfill — none exists.
- **Per-prompt drill-down.** For investigating a specific prompt, the
  `ChatGPTPromptAdsPanel` in the Reaudit dashboard at
  `/dashboard/prompts/[id]` shows the carousel cards inline with Your-Brand
  and Tracked-Competitor badges.
- **Aggregate dashboard.** The full overview, top advertisers, weekly diff,
  and gap analysis live at `/dashboard/paid-intelligence/competitor-ads` in
  the Reaudit web app.
- **Weekly cadence.** Run the diff weekly, not daily — carousel composition
  shifts slowly and daily noise drowns the signal.
- **Combine with paid intelligence.** When `get_chatgpt_competitor_ad_summary`
  shows the user's brand at 0% own share but tracked competitors are heavily
  present, that's a textbook visibility gap that the
  `paid-intelligence-campaigns` skill can convert into a ChatGPT Ads
  campaign.

## Example prompts

- "Which advertisers are dominating ChatGPT for my queries?"
- "How often do sponsored cards appear on ChatGPT for my tracked prompts?"
- "What changed in ChatGPT competitor ads this week?"
- "Who are the top 10 advertisers on ChatGPT for my prompts over the last 30 days?"
- "Show me new advertisers that started showing up on ChatGPT this week"
- "Compare my brand's share of ChatGPT sponsored cards vs. competitors"
