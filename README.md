# Reaudit AI Plugin

Official Reaudit plugin for Cursor, Claude Code, and other AI coding tools. Access your AI search visibility data, generate optimized content, and manage brand monitoring directly from your editor.

## What is Reaudit?

[Reaudit](https://reaudit.io) is the AI Search Visibility Platform. It answers the question every modern business needs to ask: **"How does AI see my brand?"**

Track, optimize, and grow your brand presence across 11 AI search engines:

| Platform | Status |
|----------|--------|
| ChatGPT | Full tracking |
| Claude | Full tracking |
| Perplexity | Full tracking |
| Google Gemini | Full tracking |
| Google AI Overview | Full tracking |
| Google AI Mode | Full tracking |
| Microsoft Copilot | Full tracking |
| Meta AI | Full tracking |
| DeepSeek | Full tracking |
| Grok | Full tracking |
| Mistral | Full tracking |

## Installation

### Cursor

Install from the [Cursor Marketplace](https://cursor.com/marketplace) (search for "reaudit"), or run:

```
/add-plugin reaudit
```

### Claude Code

```bash
claude plugin install reaudit
```

### Manual Installation

```bash
git clone https://github.com/RoseSamaras/reaudit-ai-plugin.git
```

## Authentication

The plugin connects to Reaudit's hosted MCP server at `mcp.reaudit.io`. Authentication happens automatically via **OAuth 2.0 with PKCE** — when you first use a Reaudit tool, your browser opens for a quick login. No API key configuration needed.

### Alternative: API Key

If you prefer API key authentication, generate a key in your [Reaudit Dashboard](https://reaudit.io/dashboard/tools) under **Tools > MCP Server**, then configure manually:

```json
{
  "mcpServers": {
    "reaudit": {
      "url": "https://mcp.reaudit.io/sse?apiKey=rau_your_key_here"
    }
  }
}
```

## Features

This plugin provides access to **89 tools** across these categories:

### AI Visibility
- Check your AI visibility score across 11 platforms
- View brand mentions and sentiment analysis
- Track citation sources and growth trends
- Monitor AI bot crawl activity on your site

### Prompt Tracking
- Create prompt topics for organized monitoring
- Track prompts across ChatGPT, Perplexity, Google, and more
- Get AI-generated prompt suggestions for your industry
- Analyze mention rates, sentiment, and visibility by prompt

### Content Generation
- Generate GEO-optimized blog posts, FAQs, comparisons, how-tos, and more
- Translate content into multiple languages
- Publish directly to WordPress or React/Next.js sites
- Create and schedule social media posts

### Competitive Intelligence
- Compare visibility against tracked competitors
- Find content gaps where competitors outrank you
- Monitor competitor mentions and citation patterns

### Analytics & Reporting
- Unified analytics dashboard across all connected sources
- Custom analytics queries with flexible metrics and dimensions
- Google Analytics 4 and Bing Webmaster integration
- Saved reports and automated alerts

### SEO & Optimization
- Technical SEO audits with prioritized recommendations
- Generate llms.txt files for AI discoverability
- Instant indexing for search engines
- Action grids for tracking optimization tasks

### GTM Strategy
- 6-module, 21-step Go-To-Market strategy builder
- Deep search for each strategy step
- 90-day content calendar with status tracking

## Slash Commands

- `/reaudit:visibility` — Check brand visibility scores
- `/reaudit:tracking` — Manage prompt tracking
- `/reaudit:content` — Generate AI-optimized content
- `/reaudit:competitors` — Competitor comparison
- `/reaudit:analytics` — Analytics dashboards and reports
- `/reaudit:sources` — Citation source analysis

## Skills

- **AI Visibility Audit** — Full audit of brand presence across AI search engines
- **Content Optimization** — Generate and publish GEO-optimized content
- **Competitor Analysis** — Benchmark against competitors in AI search
- **Prompt Tracking Setup** — Set up systematic prompt monitoring at scale

## Example Usage

```
> What's my AI visibility score?
> How does ChatGPT see my brand?

> Track the prompt "best project management tools"
> Which prompts mention my brand?

> Write a blog post about AI search optimization
> Publish my article to WordPress

> How do I compare against competitors in AI search?
> Add Acme Corp as a competitor

> Show me my analytics dashboard
> Which AI bots are crawling my site?

> Create a GTM strategy for my product launch
> Generate prompt suggestions for my industry
```

## Requirements

- A [Reaudit](https://reaudit.io) account
- Cursor, Claude Code, or any MCP-compatible AI client

## Documentation

- [Reaudit Platform](https://reaudit.io)
- [MCP Server Documentation](https://reaudit.io/docs/mcp)
- [Help Center](https://reaudit.io/help)

## License

MIT
