---
name: reddit-ai-trends-searcher
description: Searches Reddit for the top 10 trending AI applications within the last month. Use when the user wants to identify popular or new AI tools being discussed online.
---

# Reddit AI Trends Searcher

This skill provides a workflow for identifying the most discussed and trending AI applications on Reddit over the past month.

## When to use this skill
- Use this when the user asks for "trending AI apps", "popular AI tools", or "what's new in AI" based on social proofs from Reddit.
- Helpful for staying up-to-date with community-vetted AI technologies.

## How to use it

To find the top 10 trending AI applications, follow these steps:

1.  **Identify Relevant Subreddits:** focus searches on:
    - `r/ArtificialInteligence`
    - `r/MachineLearning`
    - `r/OpenAI`
    - `r/LocalLLaMA`
    - `r/ChatGPT`
    - `r/midjourney`

2.  **Perform Targeted Search:**
    - Use the `search_web` tool with queries like:
        - `site:reddit.com trending AI applications "last month"`
        - `site:reddit.com "top 10" AI tools August 2026` (Adjust month/year as needed based on current date)
        - `site:reddit.com "best AI apps" monthly roundup`
    - Alternatively, use the `browser_subagent` to navigate directly to `reddit.com/r/ArtificialInteligence/top/?t=month` and similar URLs.

3.  **Analyze and Extract Information:**
    - Look for recurring mentions of specific applications.
    - Pay attention to upvote counts and positive sentiment in comments.
    - Differentiate between research papers/models and actual "applications" or "tools" as requested.

4.  **Compile the Top 10 List:**
    - Provide a list of 10 applications.
    - For each app, include a brief description of what it does.
    - Mention the context of why it's trending (e.g., "Highly praised for its speed in r/LocalLLaMA").
    - Provide a link to the Reddit discussion if possible.

5.  **Present Results:** Format the output in a clean, readable Markdown list.

## Best Practices
- **Verify Recency:** Ensure the threads or posts found are actually from within the last 30 days.
- **Cross-Reference:** If an app is trending in multiple subreddits, it's a strong candidate for the top 10.
- **Avoid Hype Only:** Look for substantive reviews or "how-to" guides rather than just marketing posts.
