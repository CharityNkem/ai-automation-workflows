# AI Automation Workflows (n8n)

A set of **AI-powered automation workflows** built in [n8n](https://n8n.io), connecting LLMs to real business tools — email, spreadsheets, chat, databases, and scheduling. Each workflow is exported as JSON and can be imported into any n8n instance.

> **These are sanitized templates.** All real credentials, email addresses, document IDs, and personal details have been replaced with placeholders (e.g. `YOUR_GOOGLE_SHEET_ID`, `[Your Company]`). After importing, connect your own credentials and fill in the placeholders. No secrets are included in these files.

---

## Workflows

### 1. Client Onboarding Automation — `client-onboarding-automation.json`
Turns a submitted onboarding form into a personalised welcome flow.
- A client fills in a form (name, email, industry, goals)
- An **AI agent** generates a tailored, on-brand welcome email
- A second agent produces a concise **client profile summary**
- The welcome email is sent via Gmail, and the profile is appended to a Google Sheet

**Demonstrates:** form triggers, AI agents, structured parsing of model output, Gmail + Google Sheets integration.

### 2. Customer Support & Booking Agent — `customer-support-booking-agent.json`
A chat-based support agent for a restaurant that can answer questions and take bookings.
- Uses **retrieval-augmented generation** over a Postgres **pgvector** store for grounded answers
- Keeps conversation context with Postgres chat memory
- Can create a booking or escalate to human support

**Demonstrates:** RAG with a vector database, conversational memory, tool-using agents, human-in-the-loop escalation.

### 3. Daily Message Scheduler — `daily-message-scheduler.json`
Sends a scheduled daily message pulled from a content source.
- Runs on a **schedule trigger**
- Reads the day's content from a Google Sheet
- Conditionally formats and sends it via email

**Demonstrates:** scheduled automation, spreadsheet-driven content, conditional logic.

### 4. Team Reporting Automation — `team-reporting-automation.json`
Chases and summarises weekly team reports automatically across multiple days.
- Day-specific **schedule triggers** (e.g. reminders, follow-ups, management summaries)
- Reads submissions from a Google Sheet and detects **missing reports**
- Sends reminder/follow-up emails and an **AI-generated management summary**

**Demonstrates:** multi-branch scheduling, data checks against a source of truth, automated follow-ups, AI summarisation of operational data.

---

## What these show

- Connecting **LLMs to real tools**: Gmail, Google Sheets, Postgres/pgvector, chat, HTTP
- **AI agents** and multi-step reasoning inside automations
- **RAG** over a vector store for grounded, domain-specific answers
- Practical patterns: form-to-action, scheduled jobs, conditional branching, human escalation

---

## How to use a workflow

1. In n8n, go to **Workflows → Import from File** and choose one of the JSON files.
2. Open each node that shows a credential warning and **select your own credential** (OpenAI, Gmail, Google Sheets, Postgres, etc.).
3. Replace any placeholder values — e.g. `YOUR_GOOGLE_SHEET_ID`, `[Your Company]`, `[Your Name]`, `your-email@example.com`.
4. Test with the workflow **inactive**, then activate when it behaves as expected.

> You only need credentials for the services a given workflow uses.

---

*Built by **Charity Umoren** — medical doctor transitioning into AI engineering.*
*[LinkedIn](https://www.linkedin.com/in/charityumoren/)*
