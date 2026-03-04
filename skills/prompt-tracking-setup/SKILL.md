---
name: prompt-tracking-setup
description: Set up and manage prompt tracking to monitor brand visibility across AI search engines at scale. Use when a user wants to track how AI responds to queries about their industry, create prompt topics, schedule monitoring, or analyze prompt performance.
---

# Prompt Tracking Setup

Set up systematic prompt tracking to monitor how AI engines respond to queries relevant to your brand, industry, and competitors.

## When to Use

- User wants to start tracking their AI visibility
- User needs to create prompt topics for organized monitoring
- User wants to add new prompts to track
- User asks for prompt suggestions based on their industry
- User wants to analyze which prompts mention their brand

## Instructions

### Step 0: Understand the Project

- Use `set_active_project` to set the project context
- Use `get_project_settings` to understand the brand, industry, and competitors
- Use `list_prompt_topics` to see existing tracking setup

### Step 1: Plan Prompt Topics

Organize prompts into logical topics. Common topic structures:

- **Brand Queries** — Direct brand name searches ("What is [Brand]?", "[Brand] reviews")
- **Product Comparisons** — "Best [product category]", "[Brand] vs [Competitor]"
- **Industry Questions** — "How to [industry task]", "Best [industry] tools"
- **Problem-Solution** — "How to solve [problem your product addresses]"
- **Buying Intent** — "Should I use [Brand]?", "[Product category] pricing"

### Step 2: Generate Prompt Suggestions

- Use `generate_prompt_suggestions` to get AI-generated prompt ideas
- Provide a topic focus for more targeted suggestions
- Review suggestions and select the most relevant ones

### Step 3: Create Topics and Add Prompts

- Use `create_prompt_topic` with a name, description, and initial prompts
- For existing topics, use `add_prompts_to_topic` to expand coverage
- Aim for 10-20 prompts per topic for comprehensive coverage

### Step 4: Run Initial Tracking

- Use `track_prompt` to submit key prompts for immediate tracking
- Prompts are sent to AI engines (ChatGPT, Perplexity, Google) to check mentions
- Initial results typically available within minutes

### Step 5: Review Results

- Use `get_prompt_analytics` to see which prompts trigger brand mentions
- Identify:
  - High-visibility prompts (brand is mentioned frequently)
  - Zero-visibility prompts (brand never appears — priority for optimization)
  - Sentiment patterns (positive vs. negative mentions)
  - Platform differences (mentioned on ChatGPT but not Perplexity, etc.)

### Step 6: Iterate and Expand

- Add new prompts based on findings
- Create content targeting zero-visibility prompts (use content-optimization skill)
- Track competitor-specific prompts to monitor competitive landscape
- Review and update topics quarterly as industry language evolves

## Best Practices

- Start with 3-5 topics covering brand, product, and industry queries
- Include competitor comparison prompts for competitive intelligence
- Use natural language prompts that real users would ask AI engines
- Track prompts in multiple languages if you operate internationally
- Monitor trends over time rather than reacting to single data points
- Combine prompt tracking with content creation for a closed optimization loop
