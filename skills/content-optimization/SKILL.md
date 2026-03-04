---
name: content-optimization
description: Generate and optimize content for AI search visibility (GEO). Use when a user wants to create blog posts, FAQs, comparisons, how-tos, case studies, or any content optimized for AI discoverability. Also use for translating content or generating llms.txt files.
---

# Content Optimization for AI Search

Generate content optimized for Generative Engine Optimization (GEO) — making content discoverable and citable by AI search engines.

## When to Use

- User wants to create content that AI engines will cite
- User asks for blog posts, FAQs, comparisons, how-to guides, or case studies
- User wants to translate content for international AI visibility
- User needs an llms.txt file for AI assistants
- User wants to publish content to WordPress or a React/Next.js site
- User asks about content strategy for AI search

## Instructions

### Step 0: Establish Context

- Use `set_active_project` to set the project context
- Use `get_project_settings` to understand the brand, writing style, and target audience
- Use `search_knowledge_base` to find existing content that can inform new pieces

### Step 1: Content Planning

- Use `get_content_suggestions` to get AI-generated topic ideas based on SEO analysis
- Use `get_citation_sources` to identify what content is already being cited
- Use `get_citation_analytics` to find content gaps where the brand should have presence
- Cross-reference with competitor citations to find opportunities

### Step 2: Generate Content

- Use `generate_content` with the appropriate parameters:
  - `type`: blog_post, faq, comparison, how_to, case_study, social_post, newsletter, video_script
  - `topic`: The subject to write about
  - `projectId`: For knowledge base context and brand voice
  - `keywords`: Target keywords for the content
- The generator uses the project's knowledge base for factual accuracy and brand voice

### Step 3: Review and Edit

- Review the generated content for accuracy and brand alignment
- Use `edit_content` to refine title, body, excerpt, SEO meta fields, or tags
- Check that the content follows GEO best practices:
  - Clear, authoritative language that AI can parse and cite
  - Structured with headings, lists, and factual claims
  - Includes statistics, quotes, and citations where appropriate
  - Answers specific questions that users ask AI engines

### Step 4: Optimize for AI Discovery

- Use `generate_llms_txt` to create or update the project's llms.txt file
- This file helps AI assistants understand your business and cite your content

### Step 5: Translate (Optional)

- Use `translate_content` to create versions in other languages
- Target languages where you want AI visibility in local markets

### Step 6: Publish

- Use `list_wordpress_connections` or `list_react_connections` to find publishing targets
- Use `publish_to_wordpress` or `publish_to_react` to push content live
- Content is published with schema markup for AI discoverability

### Step 7: Social Distribution

- Use `generate_social_posts` to create social media posts from the content
- Use `schedule_social_post` to plan distribution across X/Twitter and LinkedIn

## GEO Best Practices

- Write content that directly answers questions users ask AI engines
- Include specific data points, statistics, and verifiable facts
- Structure content with clear headings and logical flow
- Use authoritative language without excessive marketing speak
- Add schema markup (handled automatically by Reaudit publishing)
- Keep content fresh — AI engines favor recently updated sources
- Create content across multiple formats (blog, FAQ, comparison) for the same topics
