# Interview Notes

## What is n8n?

n8n is a visual workflow automation and orchestration platform used to connect applications, APIs, databases, AI models, and business systems.

## What is an AI Agent?

An AI Agent is an LLM-based system that can reason about a task and use external tools to perform actions. In this project it can retrieve Google Sheets data, analyze it, and deliver the resulting report through Gmail.

## Gen AI vs AI Agent vs Agentic AI

| | Gen AI | AI Agent | Agentic AI |
|---|---|---|---|
| Main idea | Gives an answer | Performs a task | Manages a complete goal |
| Decision making | Mostly the user | Agent decides next action | Multiple systems/agents can decide and coordinate |
| Tools | Usually not required | Uses tools | Uses many tools/systems |
| Planning | No real planning | Basic planning | Advanced planning |
| Loop | One response | Multiple steps until task finishes | Multiple coordinated loops |
| Human role | Give prompt | Give task | Give goal |

## Project explanation

> I built a DataInsight Agent using n8n. The Chat Trigger receives a natural-language request. The AI Agent uses an OpenAI Chat Model to understand the request and can invoke Google Sheets to retrieve current data. The Agent analyzes the data and maintains short-term conversational context with Simple Memory. When an email report is requested, Gmail delivers the analysis. n8n acts as the orchestration layer connecting these components.
