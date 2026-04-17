# Reaudit AI Plugin

Official Reaudit plugin for Cursor, Claude Code, and other AI coding tools. Access your AI search visibility data, generate optimized content, manage paid amplification campaigns, and monitor brand presence directly from your editor.

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

This plugin provides access to **149 tools** across these categories:

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
- Generate deep prompt research reports

### Content Generation
- Generate GEO-optimized blog posts, FAQs, comparisons, how-tos, and more
- Translate content into multiple languages
- Publish directly to WordPress or React/Next.js sites
- Create and schedule social media posts
- Generate social images and cross-post across platforms

### Competitive Intelligence
- Compare visibility against tracked competitors
- Add and manage competitor tracking
- Monitor competitor mentions and citation patterns

### Paid Intelligence
- **Ad Creative Generation** — Generate AI-powered ad creatives with GEO scoring for Google, Meta, LinkedIn, and X/Twitter
- **Visibility Gap Detection** — Identify queries where your brand is absent, underperforming, or dominated by competitors
- **Campaign Management** — Create and manage ad campaigns across platforms with budget tracking
- **Platform Connections** — Connect Google Ads, Meta Ads, LinkedIn Ads, and X/Twitter Ads accounts
- **Visibility Lift Analytics** — Measure how ad campaigns correlate with AI visibility score improvements
- **ROI Dashboard** — Closed-loop reporting: ad spend vs. visibility delta, cost per visibility point, gap coverage
- **Advanced Analytics** — Search term reports, keyword/ad performance, negative keywords, bid management, cross-platform comparison
- **Meta Deep Insights** — Audience insights, creative performance, campaign status management
- **Multi-Platform Campaigns** — Create and analyze campaigns on Meta, LinkedIn, and X/Twitter directly

### Conversion Rate Optimization (CRO)
- **CRO Dashboard** — Unified view of conversion metrics, funnels, and optimization opportunities
- **Conversion Goals** — Create and track conversion goals with flexible event matching
- **Funnel Analysis** — Build multi-step funnels and identify drop-off points
- **A/B Testing** — View and analyze A/B test results with statistical significance
- **Landing Page Analysis** — Score and optimize landing pages for conversion
- **CRO Insights** — AI-generated optimization recommendations with priority scoring
- **CRO Strategy** — Create, manage, and track conversion optimization strategies

### Revenue Attribution
- Unified revenue attribution across AI referral sources
- Track which AI platforms drive conversions and revenue
- Referrer breakdown with AI source identification

### Analytics & Reporting
- Unified analytics hub across all connected sources
- Custom analytics queries with flexible metrics and dimensions
- Google Analytics 4 integration with detailed reporting
- Bing Webmaster Tools — search performance, crawl health, backlinks, URL submission
- Saved reports and automated alerts
- Configurable alert thresholds for key metrics

### Site Tracking & Integrations
- **Cloudflare Analytics** — Traffic and performance data from Cloudflare
- **AI Referral Performance** — Track visits and conversions from AI search engines
- **Page Citations** — See which pages are cited by AI platforms
- **Webflow Tracking** — AI visibility data for Webflow sites
- **Wix Tracking** — AI visibility data for Wix sites

### SEO & Optimization
- Technical SEO audits with prioritized recommendations
- SEO alerts for critical issues and ranking changes
- Generate llms.txt files for AI discoverability
- Instant indexing for search engines (Google, Bing)
- Action grids for tracking optimization tasks

### Reddit Lead Monitoring
- Monitor Reddit for brand mentions and lead opportunities
- Track and qualify Reddit leads by relevance
- Update lead status and notes for follow-up

### GTM Strategy
- 6-module, 21-step Go-To-Market strategy builder
- Deep search for each strategy step with regeneration support
- 90-day content calendar with status tracking
- Offer conversion system with pricing, value stack, and copy blocks

### Interactive MCP Apps

Five tools return rich interactive visualizations directly in the chat:

- **Visibility Score** — Gauge chart with platform-by-platform breakdown bars
- **Citation Tracker** — Donut chart with citation distribution and sparkline trends
- **AI Crawl Monitor** — Terminal-style log of AI bot activity with bot badges
- **AI Readiness Score** — Score card with category progress bars
- **Revenue Attribution** — Referrer bars and AI source breakdown with revenue metrics

These MCP Apps use the Reaudit dark theme with glass card effects and platform-specific colors.

## Slash Commands

- `/reaudit:visibility` — Check brand visibility scores
- `/reaudit:tracking` — Manage prompt tracking
- `/reaudit:content` — Generate AI-optimized content
- `/reaudit:competitors` — Competitor comparison
- `/reaudit:analytics` — Analytics dashboards and reports
- `/reaudit:sources` — Citation source analysis
- `/reaudit:paid-intelligence` — Manage paid amplification campaigns and visibility gaps
- `/reaudit:cro` — Conversion rate optimization dashboard and tools
- `/reaudit:reddit` — Reddit lead monitoring and qualification
- `/reaudit:attribution` — Revenue attribution across AI sources

## Skills

- **AI Visibility Audit** — Full audit of brand presence across AI search engines
- **Content Optimization** — Generate and publish GEO-optimized content
- **Competitor Analysis** — Benchmark against competitors in AI search
- **Prompt Tracking Setup** — Set up systematic prompt monitoring at scale
- **Paid Intelligence Campaigns** — End-to-end workflow for visibility-driven paid amplification
- **CRO Optimization** — Analyze and improve conversion rates with AI-powered insights
- **Reddit Lead Generation** — Monitor Reddit for brand mentions and qualify leads

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

> Generate a Google search ad for "best CRM software"
> What are my visibility gaps?
> Create a campaign brief for my top visibility gap
> What's my paid intelligence ROI?
> Show me the visibility lift from my ad campaigns

> Show my CRO dashboard
> Analyze my landing page conversion rate
> What are my funnel drop-off points?

> Show me revenue attribution by AI source
> Which AI platforms drive the most conversions?

> Show my Reddit leads
> Are there any SEO alerts?
> How's my Bing search performance?
```

## Privacy Policy

Reaudit collects and processes data as described in our [Privacy Policy](https://reaudit.io/privacy):

- **Data collected**: AI search visibility data, brand mentions, citation sources, and analytics from connected platforms (Google Analytics, Bing Webmaster, WordPress, Cloudflare, etc.)
- **Usage**: Data is used to generate visibility scores, content recommendations, competitive intelligence, and optimization reports for your projects
- **Storage**: All data is stored securely on Reaudit's servers with encryption at rest and in transit
- **Third-party sharing**: Data is not shared with third parties except as required to provide connected platform integrations (e.g., Google Ads, Meta Ads) that you explicitly authorize
- **Retention**: Project data is retained while your account is active and deleted upon account closure
- **Contact**: support@reaudit.io

## Requirements

- A [Reaudit](https://reaudit.io) account
- Cursor, Claude Code, or any MCP-compatible AI client

## Documentation

- [Reaudit Platform](https://reaudit.io)
- [MCP Server Documentation](https://reaudit.io/docs/mcp)
- [Help Center](https://reaudit.io/help)

## Support

- [Privacy Policy](https://reaudit.io/privacy)
- [Terms of Service](https://reaudit.io/terms)
- Email: support@reaudit.io

## License

MIT
