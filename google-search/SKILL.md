---
name: google-search
description: Search the web using DuckDuckGo and Wikipedia APIs.
---

# Google Search

## Instructions

Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **query**: Required. Extract ONLY the primary search keywords or topic (e.g., "quantum computing", "James Webb Space Telescope", "climate change research"). Remove question words, conversational text, or modifiers (e.g., do NOT include "latest", "news about", "look up", "find info about"). Provide the core search terms that would best match the user's information need.

## Constraints

- Summarize the key findings from the search results in 3-5 sentences to conserve context. Always ensure your response ends with a finished sentence.
- Always include source URLs from the results so the user can verify information.
- If the search returns no results or the results are not relevant to the user's question, briefly state this and suggest 1-2 alternative search queries that might be more helpful.
- If the user asks follow-up questions, perform a new search with a refined query based on the additional context.
- Do not fabricate information beyond what is returned in the search results.
