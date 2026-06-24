---
name: news-research
description: Search rights-cleared news and video via SimpleFeed MCP. Use when the user asks for recent articles, publisher-specific news, industry research, or verified sources instead of random web results.
---

# SimpleFeed news research

## When to use

- User needs recent news articles or video metadata on a topic
- User asks to search a specific publisher catalog
- User wants licensed, rights-cleared sources for research or briefings

## Instructions

1. Ensure SimpleFeed MCP is connected (Paid or Free server).
2. Call `list_publishers` when the user needs to know which outlets are available.
3. Call `search` with a clear natural-language query; add publisher filters when requested.
4. Summarize titles, dates, outlets, and key points. Include full article text when the Paid plan allows it.
5. Do not invent articles — only use results returned by SimpleFeed tools.

## Example prompts

- Show which publisher catalogs I can search.
- Search for recent articles about renewable energy policy in the United States. Return up to 5 results with titles and summaries.
- Find sports news from the last 3 days that mentions the NFL playoffs. Limit to 10 articles.
