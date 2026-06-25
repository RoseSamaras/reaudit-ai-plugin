---
name: tracking
description: Manage prompt tracking and monitor brand mentions across AI search engines
argument-hint: [topic or prompt]
---

# Tracking

Use the Reaudit MCP tools to help the user manage prompt tracking:

1. Use `list_prompt_topics` to see existing tracking topics (and each prompt's ID)
2. To create a new topic, use `create_prompt_topic` with prompts
3. To add prompts to an existing topic, use `add_prompts_to_topic`
4. To **edit** an existing prompt in place (fix/rewrite its text, or change its language/region), use `update_prompt` with the `promptId` — never recreate a prompt to fix it
5. To **rename a topic, enable/disable tracking, change its schedule, or its default language/region**, use `update_prompt_topic`
6. To **remove a single prompt**, use `delete_prompt`; to **remove an entire topic and all its prompts**, use `delete_prompt_topic`
7. To run tracking immediately, use `track_prompt` with a specific prompt
8. To review results, use `get_prompt_analytics`
9. For new prompt ideas, use `generate_prompt_suggestions`

## Example prompts

- "Show me my tracked prompts"
- "Create a prompt topic for product comparisons"
- "Fix the wording of that prompt instead of adding a new one"
- "Rename this topic and switch it to weekly tracking"
- "Delete the duplicate topic"
- "Track the prompt 'best project management tools'"
- "Which prompts mention my brand?"
- "Suggest new prompts to track for my industry"
