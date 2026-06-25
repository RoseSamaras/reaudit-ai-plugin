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
- User wants to edit/correct an existing prompt's wording, language, or region
- User wants to rename a topic, enable/disable it, or change its schedule
- User wants to remove a wrong, outdated, or duplicate prompt — or a whole topic
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

### Step 3b: Edit, Reorganize, or Clean Up Prompts and Topics

Use `list_prompt_topics` first to read each topic's ID and each prompt's ID and text. Then **edit in place instead of recreating** — recreating a prompt or topic loses its tracking history and creates duplicates.

- **Fix a prompt's wording (or its language/region):** use `update_prompt` with the `promptId` and the new `text`. This is the correct way to "change a prompt" — do **not** delete-and-recreate or add a second prompt.
- **Rename a topic, change its description, enable/disable scheduled tracking, change its schedule (daily/weekly/monthly), or its default language/region:** use `update_prompt_topic` with the `topicId` and only the fields to change.
- **Remove one prompt:** use `delete_prompt` — identify it by `promptId` (preferred) or exact `promptText`. The rest of the topic and its history stay intact.
- **Remove an entire topic and all of its prompts** (e.g. a duplicate or unwanted topic): use `delete_prompt_topic` with the `topicId`. Use this rather than deleting every prompt one by one.

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
