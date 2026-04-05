---
name: google-search
description: Search the web using DuckDuckGo and Wikipedia. Use when the user asks to look something up, find information, search for news, research a topic, or asks questions requiring current or factual information. Triggers on phrases like "search for", "look up", "find info about", "what is", "latest news on", or "tell me about".
license: Apache-2.0
compatibility: Requires Google AI Edge Gallery v1.0.11 or later with run_js webview support. Requires active internet connection at runtime. Compatible with tool-calling models (e.g. Gemma 4).
allowed-tools: run_js
metadata:
  author: Rahuleus12
  version: "1.1"
---
# Google Search

## Instructions

Call the `run_js` tool using `scripts/index.html` and a JSON string for `data` with the following fields:

- **query**: Required. Extract ONLY the primary search keywords or topic (e.g., `"quantum computing"`, `"James Webb Space Telescope"`, `"climate change research"`). Remove question words, conversational text, or modifiers — do NOT include words like "latest", "news about", "look up", "find info about", "search for", "what is". Provide only the core search terms that best match the user's information need.

## Response Format

After receiving results from `run_js`:

1. Summarize the key findings in 3–5 sentences. Always end on a complete sentence.
2. Include at least one source URL so the user can verify the information.
3. If results are empty or not relevant to the user's question, say so clearly and suggest 1–2 alternative search queries.
4. For follow-up questions, perform a new search with a refined query — do not reuse prior results.
5. Do not fabricate or infer information beyond what is returned in the search results.
