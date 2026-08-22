# Agent Components – Simple Explanation

## Chat Trigger

**Meaning:** Takes input from the user and starts the workflow.

**Real-world analogy:** A reception desk that receives a customer's request and sends it to the right employee.

## AI Agent

**Meaning:** Brain + decision maker. It understands the request, decides what action is needed, uses tools, analyzes tool results, performs multiple steps, and produces the final answer.

**Real-world analogy:** A data analyst who receives a task, gets the required data, performs the analysis, and prepares the result.

## OpenAI Chat Model

**Meaning:** The LLM connected to the Agent's Chat Model input. It provides language understanding and response generation.

## Simple Memory

**Meaning:** Stores short-term chat conversation context so follow-up questions can be understood.

**Important:** Memory is conversation context, not the business-data store.

## Google Sheets Tool

**Meaning:** Retrieves actual rows from the spreadsheet so the Agent can analyze current data instead of guessing.

## Gmail

**Meaning:** Delivers the analysis/report to an email recipient.

## n8n

**Meaning:** Visual workflow automation and orchestration platform that connects the trigger, AI model, Agent, tools, memory, and business actions.
