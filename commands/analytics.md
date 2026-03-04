---
name: analytics
description: Access AI visibility analytics, dashboards, and reporting
argument-hint: [metric or time range]
---

# Analytics

Use the Reaudit MCP tools to access analytics and reporting:

1. For a unified dashboard, use `get_analytics_hub`
2. For custom queries, use `query_analytics` with metrics, dimensions, and filters
3. For citation trends, use `get_citation_analytics`
4. For Google Analytics data, use `get_ga4_analytics`
5. For Bing data, use `get_bing_search_performance`
6. For AI bot crawl data, use `get_agent_analytics`
7. For saved reports, use `list_reports`, `get_report`, or `create_report`
8. For alerts, use `list_analytics_alerts` or `create_analytics_alert`

## Available metrics for query_analytics

- `mentions` — Brand mention count
- `citations` — Citation count
- `sentiment` — Sentiment score
- `visibility_rate` — Visibility percentage

## Available dimensions

- `platform` — AI engine breakdown
- `date` — Daily granularity
- `week` — Weekly granularity
- `month` — Monthly granularity

## Example prompts

- "Show me my analytics dashboard"
- "What's my citation trend over the last 30 days?"
- "Break down my mentions by AI platform"
- "Create an alert if my visibility drops below 50"
- "Show me which AI bots are crawling my site"
