# AI Agent — Multi-Tool Task Automation (n8n)

An AI Agent built in n8n that autonomously decides which tool(s) to use based on 
user intent, and can chain multiple tools together to complete complex tasks.

## Tools
- **Google Search** (via Serper API) — real-time web search
- **Google Calendar** — add/schedule events
- **Google Drive** — upload/save files
- **Summarize** — condenses text/search results

## How it works

### Workflow 1.0 — Independent Tool Use
The agent can use each tool on its own based on a single request:
- "Search for the latest AI news" → uses Google Search only
- "Add a meeting tomorrow at 4pm" → uses Google Calendar only
- "Save this text as a file" → uses Google Drive only
- "Summarize this text" → uses Summarize only

### Workflow 2.0 — Multi-Tool Chaining
The agent can combine multiple tools in sequence to complete a full task:
- "Search for the latest AI news, summarize it, and save it to Google Drive"
  → Search → Summarize → Upload (in that order)

## Skill-Based Routing
Instead of relying on default/thin tool descriptions, this agent uses explicit 
skill instructions (via the System Message) defining:
- When to use each tool
- When NOT to use each tool
- Required inputs
- How to chain tools for multi-step tasks

This makes tool selection consistent, predictable, and easy to debug.

## Setup
1. Import `workflows/ai_agent_v2.json` into n8n
2. Connect credentials: Groq (Chat Model), Google Calendar, Google Drive
3. Get a free API key from [serper.dev](https://serper.dev) for Google Search
4. Add the Serper API key as a header (`X-API-KEY`) in the HTTP Request node
5. Activate the workflow

## Screenshots
See the `docs/` folder for workflow screenshots.

## License
MIT
