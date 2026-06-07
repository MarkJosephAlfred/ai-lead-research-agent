# AI Lead Research Agent 🤖

An agentic n8n workflow that automatically researches companies and generates full B2B lead reports using AI.

## What It Does

You type a company name into a form. The AI agent:
1. Searches the web for real-time information about the company
2. Decides if it needs more information and searches again if needed
3. Writes a company overview, lead score (1-10), and a personalized cold outreach email
4. Logs everything automatically to Google Sheets

## Flow

```
Form Input → Web Research (Serper) → AI Agent (Gemini) → Google Sheets
```

The AI Agent has access to a search tool it can call autonomously — it's not just a linear pipeline. It thinks, decides, and acts.

## Stack

- **n8n** — workflow automation
- **Google Gemini** — AI model (free)
- **Serper API** — real-time Google search (free tier)
- **Google Sheets** — output logging

## Setup

1. Import `AI_Lead_Research_Agent.json` into your n8n instance
2. Add your credentials:
   - [Serper API key](https://serper.dev) → replace `YOUR_SERPER_API_KEY`
   - [Google Gemini API key](https://aistudio.google.com) → add as Google Gemini credential in n8n
   - Google Sheets OAuth2 → connect your Google account in n8n
3. Create a Google Sheet with columns: `Company`, `Overview`, `Lead Score`, `Email`
4. Update the Sheet ID in the workflow
5. Activate the workflow and open the form URL

## Example Output

**Input:** `Anthropic`

**Output:**
- Company overview of Anthropic's mission and products
- Lead score: 9/10 with reasoning
- Personalized cold outreach email ready to send
- Row automatically added to Google Sheets

## Why This Is Useful

Sales teams waste hours manually researching leads. This agent does it in seconds, at scale, for any company in the world.
