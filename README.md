# DataInsight Agent – n8n AI Data Analyst

An n8n-based AI Data Analyst workflow that accepts natural-language questions, retrieves spreadsheet data from Google Sheets, analyzes the data using an OpenAI Chat Model, maintains short-term conversation context with Simple Memory, and can deliver the analysis through Gmail.

> **Project basis:** This repository is documented from the provided DataInsight Agent implementation document and its embedded workflow snapshots. It does not include secrets, credentials, private spreadsheet data, or an n8n export that was not present in the source material.

## Architecture

```text
User
  ↓
Chat Trigger
  ↓
AI Agent  ←── OpenAI Chat Model
  │
  ├── Simple Memory
  │
  └── Google Sheets Tool
          ↓
       Data Analysis
          ↓
        Gmail
          ↓
      Email Report
```

## What this project demonstrates

- n8n workflow automation and orchestration
- AI Agent behavior and tool calling
- OpenAI Chat Model integration
- Google Sheets data retrieval
- Short-term conversational memory
- Gmail report delivery
- End-to-end AI-assisted data analysis

## Components

| Component | Purpose |
|---|---|
| Chat Trigger | Receives the user's request and starts the workflow |
| AI Agent | Understands the request, decides actions, uses tools, analyzes results, and produces the final answer |
| OpenAI Chat Model | Provides language understanding and response generation |
| Simple Memory | Stores short-term conversation context for follow-up questions |
| Google Sheets Tool | Retrieves rows from the selected spreadsheet/tab |
| Gmail | Sends the analysis/report to the requested recipient |

## Example user requests

```text
Show me total sales.
Which region has the highest sales?
Compare Mumbai and Pune sales.
Analyze the data and send the report to my email.
```

## Implementation flow

1. Prepare the Google Sheet with structured headers such as Date, Region, Product, Customer, and Sales.
2. Configure Google Sheets, OpenAI, and Gmail credentials in n8n.
3. Add **When chat message received** as the trigger.
4. Add the **AI Agent** and connect the **OpenAI Chat Model**.
5. Add **Simple Memory** to preserve conversation context.
6. Add Google Sheets using **Sheet Within Document → Get Row(s)** and select the actual spreadsheet/tab.
7. Configure Gmail **Send a message** and map the verified AI Agent response using n8n Expression mode.
8. Test the workflow from data retrieval through analysis and email delivery.

## Repository structure

```text
DataInsight-Agent/
├── README.md
├── SECURITY.md
├── assets/
│   ├── architecture-overview.png
│   ├── n8n-workflow-snapshot.png
│   └── google-sheets-tool-snapshot.png
├── docs/
│   ├── implementation-guide.md
│   ├── agent-components.md
│   ├── troubleshooting.md
│   └── interview-notes.md
├── prompts/
│   └── ai-agent-system-prompt.md
├── examples/
│   └── sample_sales_data.csv
└── workflow/
    └── workflow-design.md
```

## Important security note

Do **not** commit OpenAI API keys, Google OAuth tokens, Gmail credentials, private spreadsheet URLs, n8n webhook URLs, or other secrets. Use n8n Credentials and environment/secret management instead.

## Author

**Dnyaneshvar Khairnar**  
Pune, Maharashtra, India
