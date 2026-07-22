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

<img width="1179" height="655" alt="Screenshot 2026-07-22 113432" src="https://github.com/user-attachments/assets/26892652-d900-43a0-b131-ec1e8f28e40d" />
<img width="1321" height="945" alt="Screenshot 2026-07-22 113503" src="https://github.com/user-attachments/assets/7fceb71a-a571-496d-b0bb-070d32fb2697" />
<img width="1140" height="638" alt="Screenshot 2026-07-22 113514" src="https://github.com/user-attachments/assets/ecec4432-835d-4602-8af1-1e417606939c" />
<img width="1320" height="962" alt="Screenshot 2026-07-22 113604" src="https://github.com/user-attachments/assets/67db322d-a569-4f56-8768-9e8f65cb604e" />
<img width="1125" height="634" alt="Screenshot 2026-07-22 113617" src="https://github.com/user-attachments/assets/9c3c8120-ccf8-4268-94bc-7a3afcdd9f64" />
<img width="1294" height="942" alt="Screenshot 2026-07-22 113658" src="https://github.com/user-attachments/assets/2daf1f80-b578-4e76-997d-017fd44710f6" />
<img width="1316" height="927" alt="Screenshot 2026-07-22 113712" src="https://github.com/user-attachments/assets/e6a63f28-1e41-4571-9fca-a7fd22c5455f" />
<img width="1319" height="924" alt="Screenshot 2026-07-22 113938" src="https://github.com/user-attachments/assets/99a029e0-11b0-4d45-b4f3-154b20d892e0" />
<img width="1166" height="682" alt="Screenshot 2026-07-22 113951" src="https://github.com/user-attachments/assets/739b7aab-0be8-4c4d-a545-1e9d7059d18e" />
<img width="1318" height="942" alt="Screenshot 2026-07-22 114055" src="https://github.com/user-attachments/assets/f040ad68-8a59-4885-b907-afc7ae40a237" />
<img width="1125" height="657" alt="Screenshot 2026-07-22 114106" src="https://github.com/user-attachments/assets/8bf6c487-1cd4-41ea-8684-8deb14bb327a" />
<img width="1319" height="945" alt="Screenshot 2026-07-22 114115" src="https://github.com/user-attachments/assets/7ed0115c-6e1d-4765-b188-0b762ec489d7" />

## License
MIT
### Authot: Atika Emaan
