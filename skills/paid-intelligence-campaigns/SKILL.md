---
name: paid-intelligence-campaigns
description: End-to-end workflow for AI-visibility-driven paid amplification. Use when a user wants to find visibility gaps, generate ad creatives, manage campaigns, or analyze paid intelligence ROI across Google, Meta, LinkedIn, and X/Twitter.
---

# Paid Intelligence Campaigns

Run the full paid amplification loop: detect visibility gaps, generate GEO-scored ad creatives, launch campaigns, and measure visibility lift.

## When to Use

- User asks about visibility gaps or where their brand is missing in AI responses
- User wants to create ad campaigns targeting AI visibility blind spots
- User needs ad creative copy with GEO scoring
- User asks about paid intelligence ROI or visibility lift
- User wants to connect ad platform accounts
- User asks "How can I use ads to improve my AI visibility?"

## Instructions

### Step 0: Establish Context

- Use `set_active_project` to set the project
- Use `list_ad_platform_connections` to check which ad accounts are connected
- If no connections exist, direct the user to connect accounts in the Reaudit dashboard

### Step 1: Identify Visibility Gaps

- Use `list_visibility_gaps` to find queries where the brand is absent or underperforming
- Filter by `gapType`: absent, underperforming, competitor_dominant, geographic
- Prioritize by severity (critical > high > medium > low)
- Use `get_visibility_gap` for detailed competitor data on specific gaps

### Step 2: Generate Campaign Briefs

- For high-priority gaps, use `create_gap_campaign_brief` to generate a full brief
- The brief includes suggested headlines, keywords, target platforms, bidding range, and budget
- Review and refine the brief with the user before proceeding

### Step 3: Generate Ad Creatives

- Use `generate_ad_creative` with:
  - `platform`: google, meta, linkedin, or twitter
  - `format`: search_rsa, display, feed, stories, reels, carousel, video_script, sponsored_content, message_ad, lead_gen, promoted_post, thread
  - `targetQuery`: the AI query to target
  - `tone`: professional, casual, bold, technical, friendly
  - `variantCount`: 1-5 A/B variants
- Review the GEO score breakdown (semantic coverage, keyword variants, AI readability, authority signals)
- Use `list_ad_creatives` to see all creatives and `get_ad_creative` for details

### Step 4: Launch Campaigns

- Use `create_ad_campaign` with platform, name, budget, and schedule
- Link the generated creatives to the campaign
- Start with a conservative daily budget and scale based on results

### Step 5: Monitor Performance

- Use `list_ad_campaigns` for a campaign overview with spend, clicks, and CTR
- Use `get_ad_campaign` for detailed metrics including conversions and ROAS
- Use `get_visibility_lift` to measure the correlation between ad spend and AI visibility changes
- Check cost per visibility point to gauge efficiency

### Step 6: ROI Analysis

- Use `get_paid_intelligence_roi` for the full dashboard:
  - Total ad spend vs. visibility delta
  - Gap coverage percentage
  - Average CTR and CPC
  - Cost per visibility point
  - Top visibility lifts by query
- Present actionable recommendations based on ROI data

## Best Practices

- Start with the highest-severity visibility gaps for maximum impact
- Generate 2-3 creative variants per campaign for A/B testing
- Review GEO scores — aim for 70+ before launching
- Monitor visibility lift weekly, not daily (lift takes time to materialize)
- Reallocate budget from low-lift campaigns to high-performers
- Use the ROI dashboard monthly to justify and optimize spend
- Combine paid campaigns with organic content creation for compound effect
