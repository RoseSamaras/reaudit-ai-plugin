---
name: cro-optimization
description: Analyze and improve conversion rates using CRO tools — funnels, A/B tests, landing page analysis, and AI-powered optimization recommendations. Use when a user wants to optimize conversions, analyze funnels, review A/B tests, or improve landing pages.
---

# CRO Optimization

Analyze and improve conversion rates across your website using Reaudit's CRO tools.

## When to Use

- User asks about conversion rates or CRO
- User wants to analyze a funnel or identify drop-off points
- User asks about A/B test results
- User wants to optimize landing pages
- User needs a CRO strategy or recommendations

## Instructions

### Step 0: Establish Project Context

- Use `list_projects` to show available projects
- Use `set_active_project` with the chosen project ID

### Step 1: CRO Dashboard Overview

- Use `get_cro_dashboard` for a unified view of conversion metrics
- Note overall conversion rate, top-performing goals, and trends

### Step 2: Review Conversion Goals

- Use `list_conversion_goals` to see active goals
- Use `get_goal_conversions` for detailed conversion data per goal
- If no goals exist, suggest creating them with `create_conversion_goal`

### Step 3: Funnel Analysis

- Use `list_funnels` to see defined funnels
- Use `get_funnel_analysis` to identify drop-off points in each funnel
- Highlight the steps with the highest abandonment rates

### Step 4: A/B Test Review

- Use `list_ab_tests` to see running and completed tests
- Use `get_ab_test_results` for statistical analysis of test variants
- Identify winning variants and recommend next experiments

### Step 5: Landing Page Optimization

- Use `list_landing_pages` to see tracked pages
- Use `analyze_landing_page` to score pages and get improvement suggestions
- Prioritize pages with high traffic but low conversion rates

### Step 6: AI Recommendations

- Use `get_cro_recommendations` for AI-generated optimization suggestions
- Use `list_cro_insights` for ongoing insight tracking
- Prioritize recommendations by expected impact

### Step 7: Synthesize Report

Present a structured CRO report:

1. **Conversion Overview** — Overall rates, goal performance, trends
2. **Funnel Health** — Drop-off analysis, bottleneck identification
3. **Test Results** — A/B test outcomes and learnings
4. **Landing Page Scores** — Page-by-page conversion analysis
5. **Top Recommendations** — Prioritized actions to improve conversions
6. **Strategy** — Suggested CRO strategy for the next quarter

## Best Practices

- Always start by setting the active project
- Focus on high-traffic, low-conversion pages for maximum impact
- Recommend data-driven A/B tests before making permanent changes
- Combine funnel analysis with landing page insights for full picture
