---
name: web-search
description: Search the web using DuckDuckGo and Wikipedia. Use when the user asks about current events, facts, news, research, or any topic requiring up-to-date information.
license: Apache-2.0
compatibility: Requires Google AI Edge Gallery (run_js webview environment and index.html)
allowed-tools: run_js
metadata:
  author: your-name
  version: "1.0"
---
# Web Search

## Instructions
Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **query**: Required. Extract ONLY the primary search keywords or topic (e.g., "quantum computing", "James Webb Space Telescope"). Remove question words, conversational text, or modifiers — do NOT include "latest", "news about", "look up". Provide the core terms that best match the user's information need.

## Constraints
- Summarize key findings in 3–5 sentences. Always end with a complete sentence.
- Always include source URLs so the user can verify information.
- If results are empty or irrelevant, say so and suggest 1–2 alternative queries.
- For follow-up questions, run a new refined search — do not reuse prior results.
- Do not fabricate information beyond what the search returns.
