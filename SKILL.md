---
name: google-search
description: Search the web for current, real-time, or factual information using DuckDuckGo and Wikipedia. Use this skill whenever the user asks about current events, live data, weather, news, sports scores, prices, or any information that may have changed recently. Triggers on phrases like "search for", "look up", "find info about", "what is", "latest news on", "tell me about", "current weather", "weather in", "what's the weather", "today's", "right now", "live score", "latest update on".
license: Apache-2.0
compatibility: Requires Google AI Edge Gallery v1.0.11 or later with run_js webview support. Requires active internet connection at runtime. Compatible with tool-calling models (e.g. Gemma 4).
allowed-tools: run_js
metadata:
  author: Rahuleus12
  version: "1.2"
---
# Google Search

## Instructions

Call the `run_js` tool with the following exact parameters:
- script name: index.html
- data: A JSON string with the following fields:
  - **query**: Required. The core search keywords extracted from the user's request. Remove filler words like "search for", "look up", "find", "what is". Keep the essential topic (e.g. "Hokkaido weather", "India cricket score today", "Gemma 4 release").
  - **type**: Optional. Set to `"weather"` if the user is asking about weather, otherwise omit.

## Important
- ALWAYS call run_js for any question about current events, weather, news, scores, or recent information. Do NOT answer from memory for these topics.
- After receiving the result, summarize findings in 3–5 sentences and always include the source URL.
- If results are empty or irrelevant, say so and suggest 1–2 alternative queries.
- Do not fabricate information beyond what is returned in the result.
