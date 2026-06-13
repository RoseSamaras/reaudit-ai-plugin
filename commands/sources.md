---
name: sources
description: Analyze citation sources and find outreach opportunities
argument-hint: [domain or URL]
---

# Sources

Use the Reaudit MCP tools to analyze citation sources and outreach:

1. Use `get_citation_sources` to see which pages AI models cite. It now returns a per-engine source-type breakdown (brand, video, forum, encyclopedia, social, news, docs, other) and flags a "video opportunity" for video-friendly engines (Gemini, Google AI Overviews) — use it to decide whether to chase YouTube, Reddit, or encyclopedia mentions for a given engine
2. Use `get_citation_analytics` for citation frequency and trends
3. Use `get_citing_prompts` for a reverse lookup — given a cited URL, see which tracked prompts caused AI engines to cite it (with engines, counts, and brand-mention flag)
4. Use `get_entity_authority` to score the brand's recognition in public knowledge graphs (Wikidata QID, Wikipedia presence, detected `sameAs` profiles) into a 0-100 entity score with prioritized fixes — being a recognized entity is the prerequisite for AI citation, so run this before outreach
5. Use `extract_author_info` to get contact info from a cited URL
6. Use `list_outreach_opportunities` to see potential link building contacts
7. Use `create_outreach_opportunity` to track a new outreach target

## Example prompts

- "Which of my pages do AI models cite most?"
- "Show me my top citation sources and which engines cite YouTube"
- "Which prompts cause competitor.com to get cited?"
- "Is my brand a recognized entity? Check my Wikidata and Wikipedia presence"
- "What's my entity authority score and how do I improve it?"
- "Extract the author info from this URL"
- "What are my outreach opportunities?"
- "Which pages should I optimize for more AI citations?"
