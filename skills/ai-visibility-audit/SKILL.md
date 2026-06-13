---
name: ai-visibility-audit
description: Perform a comprehensive AI search visibility audit for a brand across 11 AI platforms. Use when a user wants to understand how AI sees their brand, check their visibility score, review brand mentions, or get a full audit of their AI search presence.
---

# AI Visibility Audit

Perform a comprehensive audit of a brand's visibility across AI search engines including ChatGPT, Claude, Perplexity, Gemini, Google AI Overview, Google AI Mode, Copilot, Meta AI, DeepSeek, Grok, and Mistral.

## When to Use

- User asks "How does AI see my brand?"
- User wants to check their AI visibility score
- User needs a full AI search presence audit
- User wants to understand brand mentions across AI platforms
- User asks about citation sources or sentiment analysis
- User wants to compare their AI visibility with competitors

## Instructions

### Step 0: Establish Project Context

- Use `list_projects` to show available projects
- Use `set_active_project` with the chosen project ID
- If only one project exists, set it automatically and confirm with the user

### Step 1: Retrieve Visibility Score

- Use `get_visibility_score` to get the overall AI visibility score
- Note the score, trend direction, and breakdown by platform
- Flag any platforms where the brand has zero visibility

### Step 2: Analyze Brand Mentions

- Use `get_brand_mentions` to get recent mentions across AI platforms
- Categorize mentions by:
  - Platform (which AI engines mention the brand)
  - Sentiment (positive, neutral, negative)
  - Context (how the brand is being discussed)
- Identify the prompts that trigger brand mentions
- Use `get_ai_responses` to read the full verbatim answer each engine returned for the highest-value prompts — quote what ChatGPT, Perplexity, and others literally said, and compare how different engines answered the same prompt

### Step 3: Review Citation Sources

- Use `get_citation_sources` to see which pages are being cited. Read the per-engine source-type breakdown (brand / video / forum / encyclopedia / social / news / docs) — if an engine leans on video, that's a YouTube opportunity; if it leans on encyclopedias, that's an entity/Wikipedia gap
- Identify your most-cited content
- Flag content gaps (topics where competitors are cited but you are not)
- Use `get_citation_analytics` for trend data on citation growth
- Use `get_citing_prompts` on a competitor or third-party URL that keeps appearing — see exactly which prompts cause it to be cited, so you know which queries to target with your own content

### Step 3.5: Score Entity Authority

- Use `get_entity_authority` to check whether the brand is a recognized entity in public knowledge graphs (Wikidata QID, Wikipedia presence, detected `sameAs` profiles), returned as a 0-100 score with established/emerging/unrecognized status
- Entity recognition is now the prerequisite for AI citation (branded web mentions correlate with AI citations far more than backlinks), so a low entity score explains low visibility even when content is strong
- Surface the tool's prioritized recommendations (create a Wikidata item, add an Organization `sameAs` block, earn consistent named mentions) as early actions

### Step 4: Competitor Comparison

- Use `get_competitor_comparison` to see how the brand stacks up
- Identify where competitors outrank the brand in AI responses
- Note competitor strengths and the brand's relative weaknesses

### Step 5: Check Prompt Analytics

- Use `get_prompt_analytics` to review tracked prompt performance
- Identify prompts with high visibility vs. those where the brand is absent
- Use `list_prompt_topics` to see which topics are being monitored

### Step 6: Review Bot Crawl Activity

- Use `get_agent_analytics` to check which AI bots are crawling the site
- Note crawl frequency by bot (GPTBot, ClaudeBot, PerplexityBot, etc.)
- Identify pages that attract the most AI bot traffic
- Use `check_crawlability` to confirm those bots can actually reach key pages — it combines robots.txt analysis with live fetches that impersonate each bot's User-Agent, catching silent WAF/CDN blocks that crawl logs alone won't reveal. It's free and consumes no credits.

### Step 7: Synthesize the Audit Report

Present a structured report:

1. **Visibility Score** — Overall score, trend, and platform breakdown
2. **Brand Presence** — Where the brand appears, mention frequency, sentiment
3. **Citation Health** — Top cited pages, citation growth trend, gaps
4. **Competitive Position** — Ranking vs. competitors, strengths, weaknesses
5. **Crawl Activity** — Which AI bots visit, how often, which pages they favor
6. **Key Findings** — 3-5 actionable insights
7. **Recommended Actions** — Prioritized next steps to improve AI visibility

## Best Practices

- Always start by setting the active project
- Present numbers with context ("Your score of 72 is up 8 points from last month")
- Compare against competitors whenever data is available
- Prioritize recommendations by impact and effort
- Link findings to specific content or pages when possible
- If prompt tracking is not set up, recommend the user create prompt topics
