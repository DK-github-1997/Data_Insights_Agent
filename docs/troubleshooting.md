# Troubleshooting

## Gmail displays `{{ $json.output }}` literally

The value is being treated as plain text rather than an n8n expression. Switch the Message field to Expression mode and map the actual AI Agent output from the input panel.

## Google Sheets shows `undefined`

The spreadsheet/document value is missing. Select the actual spreadsheet and correct sheet/tab, then execute the Google Sheets node independently.

## Gmail sends successfully but contains the wrong content

Open **AI Agent → Output** and identify the exact field containing the final answer. Map that verified field into Gmail instead of assuming the field name.

## AI Agent cannot answer spreadsheet questions

Confirm that Google Sheets **Get Row(s)** returns real rows and that the Google Sheets node is connected as a tool when tool calling is intended.

## Follow-up questions lose context

Verify that Simple Memory is connected to the Agent's Memory input and that the same chat/session context is being maintained.
