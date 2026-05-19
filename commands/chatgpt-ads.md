---
name: chatgpt-ads
description: ChatGPT Ads (OpenAI) performance reporting and Adthena-style competitor ad intelligence for tracked prompts
argument-hint: [action, campaign id, or date range]
---

# ChatGPT Ads (OpenAI)

Use the Reaudit MCP tools to surface ChatGPT Ads performance from the OpenAI
Advertiser API and Adthena-style intelligence on which advertisers dominate
the sponsored carousels on ChatGPT Search.

## Performance Reporting

1. Use `get_chatgpt_ads_summary` for the 7-day rollup with connection status,
   read from the synced `AdPerformance` collection (fast, no OpenAI API
   quota usage)
2. Use `get_chatgpt_ads_performance` for a configurable 1–90 day daily series
   covering impressions, clicks, spend, CTR, and CPC
3. Use `get_chatgpt_campaign_insights` for a live pull from the OpenAI
   Advertiser API for a specific campaign with `since`, `until`, and
   `granularity` (`daily` or `none`)
4. Use `get_chatgpt_ad_group_insights` for the same shape, scoped to an ad
   group
5. Use `get_chatgpt_ad_insights` for the same shape, scoped to a single ad
   (chat_card creative)

## Competitor Ad Intelligence (Adthena-style)

Every tracked-prompt run on ChatGPT Search captures the sponsored carousel
cards alongside the organic answer. These tools aggregate that across your
project's tracked prompts:

6. Use `get_chatgpt_competitor_ad_summary` for ad-presence rate, total
   carousel cards, unique advertisers, and the own / tracked-competitor /
   other split
7. Use `get_chatgpt_top_advertisers` for a ranked list of advertisers seen
   in ChatGPT sponsored cards, each tagged as own brand, tracked competitor,
   or other
8. Use `get_chatgpt_competitor_ad_changes` for the "what changed this week"
   diff (last 7 days vs. prior 7 days): new advertisers, lost advertisers,
   and presence-rate shifts

## Creating ChatGPT Ads Campaigns

For creative generation and full CRUD over ChatGPT Ads campaigns, use the
`/reaudit:paid-intelligence` command with:

- `generate_ad_creative` → `platform: 'openai'`, `format: 'chat_card'`
- `create_ad_campaign` → `platform: 'openai'`

## Example prompts

- "What's my ChatGPT Ads performance this week?"
- "Show my ChatGPT Ads daily performance over the last 30 days"
- "Get insights for my ChatGPT Ads campaign abc-123 between 2026-04-01 and 2026-04-30"
- "Show ad-group-level insights for ad group xyz over the last 14 days"
- "Which advertisers are dominating ChatGPT for my queries?"
- "How often do sponsored cards appear on ChatGPT for my tracked prompts?"
- "What changed in ChatGPT competitor ads this week?"
- "Who are the top 10 advertisers on ChatGPT for my prompts in the last 30 days?"
