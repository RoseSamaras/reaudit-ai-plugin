---
name: visibility
description: Check AI search visibility score and brand presence across AI platforms
argument-hint: [project name]
---

# Visibility

Use the Reaudit MCP tools to help the user check their AI search visibility:

1. Use `list_projects` to find the right project, then `set_active_project`
2. Use `get_visibility_score` to get the overall score and platform breakdown
3. Use `get_brand_mentions` to see recent mentions across AI engines
4. Use `get_ai_responses` to read the full verbatim answer each AI engine returned for a prompt — what they literally said about the brand, with brands and citations parsed out
5. Use `check_crawlability` to confirm AI bots (GPTBot, ClaudeBot, PerplexityBot, OAI-SearchBot, Google-Extended, CCBot) can actually reach the site — it's free and catches silent WAF/CDN blocks
6. Present the score with trend context and key platform highlights

## Example prompts

- "What's my AI visibility score?"
- "How does ChatGPT see my brand?"
- "What did ChatGPT and Perplexity actually say about my brand last week?"
- "Can GPTBot and ClaudeBot actually reach my homepage?"
- "Show me my brand mentions across AI platforms"
- "Which AI engines mention my brand the most?"
