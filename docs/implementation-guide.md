# Implementation Guide #

## 1. Prepare Google Sheet

Create the data sheet with clear headers such as `Date`, `Region`, `Product`, `Customer`, and `Sales`. Share the sheet with the Google account used by n8n.

## 2. Configure Credentials

Add the Google Sheets, OpenAI, and Gmail credentials in n8n.

## 3. Add Chat Trigger

Add **When chat message received**. This receives the user's question and starts the workflow.

Example input:

```text
Show me total sales
```

The source document also identifies chat context fields such as `chatInput`, `sessionId`, and `action`.

## 4. Add AI Agent + OpenAI Model

Add the AI Agent and connect the OpenAI Chat Model. The Agent should be instructed to retrieve, analyze, and explain spreadsheet data.

## 5. Add Simple Memory

Connect Simple Memory to the Agent's Memory input so follow-up questions can use the current conversation context.

Example:

```text
User: Show Mumbai sales.
User: Compare it with Pune.
```

## 6. Add Google Sheets Tool

Use:

```text
Google Sheets → Sheet Within Document → Get Row(s)
```

Select the actual spreadsheet and tab. Test the node first and confirm that real rows are returned.

## 7. Add Gmail

Configure Gmail → Send a message. Set the recipient and subject. Map the verified AI Agent response into the Message field using **Expression mode**.

## 8. Test End-to-End

Test in this order:

1. `What is the total sales?`
2. `Which region has the highest sales?`
3. `Analyze the data and send the report to my email.`

## Expected flow

```text
User → Chat Trigger → AI Agent → Google Sheets → Analyze → Gmail → Report
```
