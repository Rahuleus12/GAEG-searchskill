---
name: google-search
description: Search the web for information on any topic and return a summary of top results.
---

# Google Search

## Examples

* "Search for the latest news about AI"
* "Look up information about space exploration"
* "Find info about climate change research"
* "What is the latest on AI regulations?"

## Instructions

Call the `run_js` tool with the following exact parameters:

- script name: `index.html`
- data: A JSON string with the following field:
  - `query`: String. The search query to look up on the web.

## Rules

- Always include source URLs so the user can verify information
- If the search returns no results, suggest alternative queries
- Summarize the key findings from the results rather than just listing them
- If the user asks follow-up questions, perform a new search with a refined query