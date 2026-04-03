---
name: google-search
description: Search the web for information on any topic. Returns a summary of top search results with titles, snippets, and source links. Use when the user asks to "search for", "look up", "find info about", "google", "search the web", "what's the latest on", or any query that requires up-to-date information from the internet.
---

# Google Search

## What This Skill Does
Searches the web for the given query and returns a formatted summary of the top results including titles, snippets, and source URLs. Useful for finding current information, looking up facts, researching topics, and getting quick answers from the internet.

## Instructions

When the user wants to search for something:

### Step 1: Extract the search query
- Identify the core search query from the user's message
- Clean up conversational filler but preserve the key search intent
- If the query is vague, use the most specific interpretation

### Step 2: Call the run_js tool

Call the `run_js` tool with the following parameters:
- script name: `index.html`
- data: A JSON string with this field:
  - `query`: String. The search query to look up on the web.

### Step 3: Present the results

After running the JS tool, show the user:
1. A brief summary answering their question based on the search results
2. The top results with titles, snippets, and clickable source links
3. If relevant, suggest follow-up searches or related topics

## Example

User: "Search for the latest news about AI regulations"

You extract:
- query: "latest news about AI regulations"

Then call run_js and show the results in a clean, readable format with:
- A brief answer summarizing the findings
- Numbered list of top results with titles, snippets, and URLs

## Rules
- Always include the source URLs so the user can verify information
- If the search returns no results, suggest alternative queries
- For ambiguous queries, use the most likely intent
- Summarize the key findings from the results rather than just listing them
- If the user asks follow-up questions about search results, perform a new search with a refined query