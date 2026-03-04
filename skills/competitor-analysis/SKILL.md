---
name: competitor-analysis
description: Analyze and compare AI search visibility against competitors. Use when a user wants to benchmark their brand, find competitive gaps, understand who AI recommends instead of them, or build a competitive intelligence report.
---

# Competitor Analysis

Compare your brand's AI search visibility against competitors to identify gaps, opportunities, and strategic advantages.

## When to Use

- User asks "Who does AI recommend instead of me?"
- User wants to benchmark against specific competitors
- User needs a competitive intelligence report
- User wants to find visibility gaps where competitors outperform them
- User asks about market positioning in AI search results

## Instructions

### Step 0: Establish Context

- Use `set_active_project` to set the project
- Use `list_competitors` to see currently tracked competitors
- If no competitors are tracked, use `add_competitor` to add them

### Step 1: Head-to-Head Comparison

- Use `get_competitor_comparison` to get a side-by-side visibility comparison
- Compare:
  - Overall visibility scores
  - Mention frequency across platforms
  - Sentiment analysis (who is perceived more positively)
  - Citation counts and sources

### Step 2: Platform-Level Analysis

- Use `query_analytics` with dimensions `["platform"]` and competitor filters
- Identify which AI platforms favor which brands
- Find platforms where your brand has zero presence but competitors are strong

### Step 3: Citation Source Analysis

- Use `get_citation_sources` for your brand's cited pages
- Compare against competitor mention patterns from `get_brand_mentions`
- Identify content types that get cited for competitors but not for you

### Step 4: Prompt Gap Analysis

- Use `get_prompt_analytics` to see which prompts trigger competitor mentions
- Identify high-value prompts where competitors appear but your brand does not
- Use `generate_prompt_suggestions` to discover new monitoring opportunities

### Step 5: Synthesize Competitive Report

Present findings as:

1. **Competitive Landscape** — Overview of all tracked competitors with scores
2. **Your Strengths** — Where you outperform competitors
3. **Competitive Gaps** — Where competitors outperform you, ranked by impact
4. **Platform Breakdown** — Which AI engines favor which brands
5. **Content Opportunities** — Topics where competitors are cited but you are not
6. **Action Plan** — Prioritized steps to close gaps and extend leads

## Best Practices

- Track at least 3-5 direct competitors for meaningful analysis
- Re-run comparison monthly to track progress
- Focus on high-intent prompts where competitor mentions drive business value
- Use content optimization skill to create content targeting identified gaps
- Monitor new competitors entering the space with `add_competitor`
