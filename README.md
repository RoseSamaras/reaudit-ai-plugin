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

This plugin provides access to **189 tools** across these categories:

### AI Visibility
- Check your AI visibility score across 11 platforms
- View brand mentions and sentiment analysis
- Read the full verbatim AI engine responses per prompt — exactly what ChatGPT, Perplexity, and others said about your brand
- Track citation sources and growth trends, now with a per-engine source-type breakdown (brand, video, forum, encyclopedia, social, news, docs) and a "video opportunity" flag for engines that lean on YouTube
- Reverse citation lookup — see which prompts cause any URL to be cited
- Monitor AI bot crawl activity on your site

### Prompt Tracking
- Create prompt topics for organized monitoring
- Track prompts across ChatGPT, Perplexity, Google, and more
- Add prompts to existing topics, or delete a single wrong/outdated/duplicate prompt without recreating the topic
- Get AI-generated prompt suggestions for your industry
- Analyze mention rates, sentiment, and visibility by prompt
- Generate deep prompt research reports

### Content Generation
- Generate GEO-optimized blog posts, FAQs, comparisons, how-tos, and more — every generation returns a 0-100 GEO answer-shape score (answer-first lead, question-form headings, table, stat density, visible freshness date) plus quality warnings
- Translate content into multiple languages
- Publish directly to WordPress or React/Next.js sites
- Create and schedule social media posts
- Generate social images and cross-post across platforms

### Content Audit
- **Content inventory** — build an auditable inventory of your existing pages from Reaudit-generated content, WordPress, Shopify, and/or your sitemap
- **AI search visibility scoring** — score each page on five checks: GEO answer-shape (extractability for AI engines), freshness, readability, entity gap (does the page actually name your brand, products, and core topics?), and brand-voice drift
- **Severity-ranked findings** — every issue comes with the page URL, a specific message, and a recommendation
- **Grounded fixes** — generate an AI-optimized rewrite for Reaudit-managed pages, or a copyable fix suggestion for external pages

### Competitive Intelligence
- Compare visibility against tracked competitors
- Add and manage competitor tracking
- Monitor competitor mentions and citation patterns
- **Content Radar** — detect, inspect, and AI-analyze competitor content as it is published (angle, topics, gaps, opportunities), and trigger fresh scans of tracked sources

### Paid Intelligence
- **Ad Creative Generation** — Generate AI-powered ad creatives with GEO scoring for Google, Meta, LinkedIn, X/Twitter, and ChatGPT Ads (OpenAI `chat_card` format)
- **Visibility Gap Detection** — Identify queries where your brand is absent, underperforming, or dominated by competitors
- **Campaign Management** — Create and manage ad campaigns across platforms with budget tracking
- **Platform Connections** — Connect Google Ads, Meta Ads, LinkedIn Ads, X/Twitter Ads, and ChatGPT Ads (OpenAI) accounts
- **Visibility Lift Analytics** — Measure how ad campaigns correlate with AI visibility score improvements
- **ROI Dashboard** — Closed-loop reporting: ad spend vs. visibility delta, cost per visibility point, gap coverage
- **Advanced Analytics** — Search term reports, keyword/ad performance, negative keywords, bid management, cross-platform comparison
- **Meta Deep Insights** — Audience insights, creative performance, campaign status management
- **Multi-Platform Campaigns** — Create and analyze campaigns on Meta, LinkedIn, X/Twitter, and ChatGPT Ads (OpenAI) directly
- **ChatGPT Ads (OpenAI)** — Full integration with the OpenAI Advertiser API: 7-day rollups, configurable 1–90 day daily performance series, and live campaign / ad-group / ad insights with `since`, `until`, and `granularity` controls
- **Paid Analytics Alerts** — Configure anomaly alerts on six new paid metrics sourced from ChatGPT Ads: `paidSpend`, `paidClicks`, `paidImpressions`, `paidCtr`, `paidCpc`, `paidConversions`

### ChatGPT Competitor Ad Intelligence (Adthena-style)
- **Sponsored Carousel Capture** — Every tracked-prompt run on ChatGPT Search captures the sponsored carousel cards alongside the organic answer
- **Ad-Presence Summary** — See how often sponsored cards appear across your tracked prompts, total card volume, unique advertisers, and the own / tracked-competitor / other split
- **Top Advertisers** — Ranked list of advertisers dominating your queries, tagged as own brand, tracked competitor, or other
- **Weekly Diff** — "What changed this week" view: new advertisers, lost advertisers, and presence-rate shifts over the last 7 days vs. the prior 7

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

### AI Commerce (Shopping Visibility)
- **Shopping AI Visibility** — How your products surface in AI-driven Shopping experiences via your connected Google Merchant Center account
- **Competitive Share of Voice** — Relative Shopping visibility against tracked competitor domains
- **Organic Shopping Funnel** — Impressions, clicks, and CTR for your Shopping surfaces
- **Attribute Completeness** — How well your feed describes products (color, material, gtin, size) so AI systems can understand and recommend them
- **Feed Issue Detection** — Critical, error, and suggestion-level problems that make products hard for AI to recommend, with affected product counts

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
- **Entity Authority** — score your brand's recognition in public knowledge graphs (Wikidata QID, Wikipedia presence, detected `sameAs` profiles) into a 0-100 entity score with established/emerging/unrecognized status and prioritized fixes — entity recognition is now the prerequisite for AI citation
- **ChatGPT eligibility (Bing-grounded)** — optimization reports flag whether your pages are indexed in Bing, since a page Bing hasn't indexed cannot be cited in ChatGPT Search
- **AI agent readiness scan** — 20 checks across discoverability, content accessibility, bot access control, API/Auth/MCP discovery, and agentic commerce, rolled into a 0-5 readiness level with per-check fix guidance
- Free AI-bot crawlability check — confirm GPTBot, ClaudeBot, PerplexityBot, OAI-SearchBot, Google-Extended, and CCBot can actually reach a page (catches silent WAF/CDN blocks, consumes no credits)
- SEO alerts for critical issues and ranking changes
- Generate llms.txt files for AI discoverability
- Instant indexing for search engines (Google, Bing)
- Action grids for tracking optimization tasks

### GitHub Auto-Fixes
- **Repo connections** — check whether a project has a GitHub repo connected
- **Propose fixes** — turn audit findings into a patch preview before opening a PR
- **Open SEO and GEO fix PRs** — write the fix and open a pull request directly in your repo on a fresh branch
- Reaudit never pushes to your default branch. Every change is a pull request you review and merge.

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
- `/reaudit:content-audit` — Audit existing content for AI search visibility and fix the gaps
- `/reaudit:competitors` — Competitor comparison
- `/reaudit:analytics` — Analytics dashboards and reports
- `/reaudit:shopping` — Google Merchant Center Shopping AI visibility and product feed health
- `/reaudit:sources` — Citation source analysis
- `/reaudit:paid-intelligence` — Manage paid amplification campaigns and visibility gaps
- `/reaudit:chatgpt-ads` — ChatGPT Ads (OpenAI) performance and Adthena-style competitor ad intelligence
- `/reaudit:cro` — Conversion rate optimization dashboard and tools
- `/reaudit:reddit` — Reddit lead monitoring and qualification
- `/reaudit:attribution` — Revenue attribution across AI sources
- `/reaudit:github` — Open pull requests that fix SEO and GEO issues found in your audits

## Skills

- **AI Visibility Audit** — Full audit of brand presence across AI search engines
- **Content Optimization** — Generate and publish GEO-optimized content
- **Content Audit** — Inventory existing pages, score them for AI search visibility, and draft grounded fixes
- **Competitor Analysis** — Benchmark against competitors in AI search
- **Prompt Tracking Setup** — Set up systematic prompt monitoring at scale
- **Shopping Visibility** — Analyze Google Merchant Center Shopping AI visibility, competitive share, and product feed health
- **Paid Intelligence Campaigns** — End-to-end workflow for visibility-driven paid amplification
- **ChatGPT Competitor Ads** — Adthena-style workflow for tracking which advertisers dominate sponsored carousels on ChatGPT Search and what changed this week
- **CRO Optimization** — Analyze and improve conversion rates with AI-powered insights
- **Reddit Lead Generation** — Monitor Reddit for brand mentions and qualify leads
- **GitHub PR Fixing** — Connect a repo, scan an audit, open pull requests that fix SEO and GEO issues

## Example Usage

```
> What's my AI visibility score?
> How does ChatGPT see my brand?
> What did ChatGPT and Perplexity actually say about my brand last week?
> Can GPTBot and ClaudeBot actually reach my homepage?
> Which prompts cause competitor.com to get cited?

> Track the prompt "best project management tools"
> Which prompts mention my brand?
> Fix the wording of that prompt instead of adding a new one
> Rename this topic and switch it to weekly tracking
> Delete the outdated 2025 prompt from my Greek beauty topic
> Delete the whole duplicate prompt topic
> Scan my site for AI agent readiness and tell me what's failing
> What new content have my competitors published this week?

> Is my brand a recognized entity? Check my Wikidata and Wikipedia presence
> What's my entity authority score and how do I improve it?
> Can my pages be cited in ChatGPT? Are they indexed in Bing?
> Which engines cite YouTube for my prompts — where's my video opportunity?

> Write a blog post about AI search optimization
> Publish my article to WordPress

> Audit my existing content for AI search visibility
> Which of my pages are stale or hard for AI to cite?
> Import my sitemap and run a content audit
> Generate a fix for the lowest-scoring page

> How do I compare against competitors in AI search?
> Add Acme Corp as a competitor

> Show me my analytics dashboard
> Which AI bots are crawling my site?

> Create a GTM strategy for my product launch
> Generate prompt suggestions for my industry

> Generate a Google search ad for "best CRM software"
> Generate a ChatGPT chat_card ad for "AI search visibility platform"
> What are my visibility gaps?
> Create a campaign brief for my top visibility gap
> What's my paid intelligence ROI?
> Show me the visibility lift from my ad campaigns

> What's my ChatGPT Ads performance this week?
> Show my ChatGPT Ads daily performance over the last 30 days
> Get insights for my ChatGPT Ads campaign abc-123 between 2026-04-01 and 2026-04-30
> Alert me when my ChatGPT Ads paidSpend doubles week over week

> Which advertisers are dominating ChatGPT for my queries?
> How often do sponsored cards appear on ChatGPT for my tracked prompts?
> What changed in ChatGPT competitor ads this week?

> Show my CRO dashboard
> Analyze my landing page conversion rate
> What are my funnel drop-off points?

> Show me revenue attribution by AI source
> Which AI platforms drive the most conversions?

> How visible are my products in Shopping?
> What's my Shopping share of voice vs competitors?
> Which product attributes are incomplete in my feed?
> What feed issues are hurting how AI recommends my products?

> Show my Reddit leads
> Are there any SEO alerts?
> How's my Bing search performance?

> Which of my projects has a GitHub repo connected?
> Open a pull request that fixes the SEO issues in my latest audit
> Preview the fixes you would propose for the missing-llms.txt recommendation
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
