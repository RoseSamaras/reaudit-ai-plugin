<p align="center"><img src="assets/logo.png" alt="Reaudit" width="128" height="128"></p>

# dsh-reaudit

[Reaudit](https://reaudit.io) for [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness): a bundle that mounts the hosted Reaudit MCP server (`https://mcp.reaudit.io/mcp`) through the in-box `@deepseek-ai/dsh-mcp-client` bridge.

The agent gets Reaudit's tools as `mcp__reaudit__*` (238 at the time of writing; the server's `/health` endpoint reports the live count), covering:

- **AI visibility**: how ChatGPT, Perplexity, Gemini, Google AI Overviews and other engines answer your tracked prompts, visibility scores, competitor comparisons, citation sources and sentiment (`get_visibility_score`, `get_competitor_comparison`, `get_citation_sources`, `get_sentiment_report`).
- **Site health**: audits and recommendations, crawlability and agent-readiness checks (`run_audit`, `get_audit_recommendations`, `check_crawlability`, `scan_agent_readiness`).
- **Content**: generation, editing, translation and publishing to WordPress (`generate_content`, `edit_content`, `translate_content`, `publish_to_wordpress`).
- **Search and analytics**: Google Search Console, GA4 and Bing Webmaster data in one place, plus each source on its own (`get_analytics_hub`, `get_ga4_analytics`, `get_bing_search_performance`).
- **Social and community**: post generation and scheduling, Reddit opportunities (`generate_social_posts`, `schedule_social_post`, `get_reddit_opportunities`).

Nothing runs locally besides the bridge: the tools execute on Reaudit's server against your account.

## Install

```sh
dsh plugin --profile <profile> add github:RoseSamaras/reaudit-ai-plugin#path:/packages/dsh-reaudit
```

## Authenticate

1. Create an API key at [reaudit.io](https://reaudit.io/dashboard/tools) under **Tools → MCP Server** (it starts with `rau_`).
2. Make it available to dsh as `REAUDIT_API_KEY`:

   ```sh
   export REAUDIT_API_KEY=rau_your_key_here
   dsh --profile <profile>
   ```

The key is sent as an `Authorization: Bearer` header, not in the URL, so it stays out of access logs. Without it the server answers 401 and dsh starts without the Reaudit tools (`failOnStartupError: false`).

## Configure

Long-running tools (audits, strategy research, content generation) take minutes, so the bundle raises the per-call timeout to 5 minutes. To change it, or the endpoint, repeat the row's id **without** `insert` in a later layer (your profile's `cordis.patch.yml` or a `--patch` file):

```yaml
- id: mcp-reaudit
  name: '@deepseek-ai/dsh-mcp-client'
  config:
    serverName: reaudit
    transport: streamable-http
    url: https://mcp.reaudit.io/mcp
    headers:
      Authorization: !!js "`Bearer ${process.env.REAUDIT_API_KEY || ''}`"
    toolCallTimeoutMs: 600000
```

## License

MIT
