---
name: google-search
description: Search the web for real-time information, news, YouTube video details, and weather. Use this skill when the user asks about current news, latest updates, weather in a city, or wants info about a YouTube video URL. ALWAYS use this skill instead of answering from memory for anything current or recent. Triggers on phrases like "search for", "look up", "latest news", "weather in", "YouTube video info", "what is this video", "tell me about", "current", "today", "recent", "breaking news", "find info about".
license: Apache-2.0
compatibility: Requires Google AI Edge Gallery v1.0.11 or later with run_js webview support. Requires active internet connection. Compatible with tool-calling models (e.g. Gemma 4).
allowed-tools: run_js
metadata:
  author: Rahuleus12
  version: "2.0"
---
# Web Search Skill

## Instructions

Call the `run_js` tool with the following exact parameters:
- script name: index.html
- data: A JSON string with the following fields:

| Field | Required | Description |
|-------|----------|-------------|
| `query` | Yes (unless `url` given) | Core search keywords. Strip filler words like "search for", "look up", "find". E.g. `"Hokkaido weather"`, `"AI news today"`, `"Gemma 4 release"` |
| `url` | For YouTube | The full YouTube video URL when user shares a link. E.g. `"https://youtu.be/abc123"` |
| `type` | Optional | One of: `"weather"`, `"news"`, `"youtube"`. Omit for general search. |

## When to use each type

- `"weather"` — user asks about weather, temperature, or forecast in a location
- `"news"` — user asks about latest news, recent events, headlines, updates
- `"youtube"` — user shares a YouTube URL or asks for video info/details
- No type — general factual lookup, definitions, Wikipedia-style questions

## Rules
- ALWAYS call run_js for weather, news, YouTube links, or anything current. Do NOT answer these from memory.
- After receiving the result, summarize in 3–5 clear sentences and include source URLs.
- If the result has an `error` field, report it and suggest alternative queries.
- Never fabricate information beyond what is returned.
