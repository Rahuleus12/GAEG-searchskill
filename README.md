gsearchskill/README.md
# Google Search Skill for AI Edge Gallery

A web search skill for the [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery) app that enables on-device LLMs to search the web for information.

## What It Does

This skill allows the LLM to search the web using the DuckDuckGo Instant Answer API and Wikipedia's search API. When a user asks to look something up, the skill:

1. Queries DuckDuckGo for instant answers and related topics
2. Falls back to Wikipedia search for encyclopedic information
3. Returns formatted results with titles, snippets, and source links

## Installation

### Option 1: Load from URL
Host this `google-search` folder on a web server (e.g., GitHub Pages), then in the AI Edge Gallery app:
1. Go to **Agent Skills** → **Skills** tab
2. Tap **(+)** → **Load skill from URL**
3. Enter the URL pointing to the `google-search` folder

### Option 2: Import from local file
1. Push the `google-search` folder to your Android device (e.g., to the `Download` folder)
   ```bash
   adb push google-search/ /sdcard/Download/
   ```
2. In the AI Edge Gallery app, go to **Agent Skills** → **Skills** tab
3. Tap **(+)** → **Import local skill**
4. Select the `google-search` directory

## Usage Examples

Once installed, try these prompts in the Agent Skills chat:

- "Search for the latest news about quantum computing"
- "Look up information about the James Webb Space Telescope"
- "Find info about climate change research"
- "What is the latest on AI regulations?"

## Skill Structure

```
google-search/
├── SKILL.md          # Skill metadata and LLM instructions
└── scripts/
    └── index.html    # JavaScript logic for web search
```

## How It Works

1. The **SKILL.md** tells the LLM when to trigger this skill (when the user wants to search the web) and how to call the `run_js` tool
2. The **scripts/index.html** runs in a hidden webview and performs the actual search via:
   - DuckDuckGo Instant Answer API (`https://api.duckduckgo.com/`)
   - Wikipedia Search API (`https://en.wikipedia.org/w/api.php`) as a fallback
3. Results are returned as a JSON string with formatted search results

## Requirements

- An active internet connection (the search APIs are called at runtime)
- AI Edge Gallery app v1.0.11 or later
- A model that supports tool/function calling (e.g., Gemma 4)

## License

Apache License 2.0