# Workflow Design

## Logical design

```text
When chat message received
        ↓
     AI Agent
      ↙   ↘
Memory   Tools
          ├── Google Sheets → Get Row(s)
          └── Gmail → Send Message
        ↓
   Final response/report
```

## Node responsibilities

- **When chat message received:** starts the workflow.
- **OpenAI Chat Model:** language understanding and generation.
- **AI Agent:** task reasoning, tool selection, analysis, and final response.
- **Simple Memory:** short-term conversation context.
- **Google Sheets:** data retrieval.
- **Gmail:** report delivery.

## n8n export note

The source material contains workflow screenshots and implementation documentation, but not a native n8n workflow-export JSON. Therefore this repository intentionally does not claim to provide an import-ready workflow JSON.
