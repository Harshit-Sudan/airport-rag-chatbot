# Airport Info RAG Chatbot

This is an AI chatbot I built that answers airport-related questions using RAG (Retrieval-Augmented Generation). I made it using n8n, Google Gemini, and Google Sheets as the knowledge base.

## What it does
The chatbot answers questions about things like terminal info, baggage rules, parking, and airport services by pulling data from a Google Sheet. If someone asks something outside these topics, it says it can only help with airport-related questions instead of making up an answer.

## Tech used
- n8n (self-hosted using Docker)
- Google Gemini 2.5 Flash (the LLM)
- Google Sheets (used as the knowledge base)
- Simple Memory (so it remembers the conversation)

## How it works
Chat message comes in → AI Agent processes it → Agent is connected to:
- Google Gemini (generates the response)
- Simple Memory (keeps track of conversation context)
- Google Sheets (looks up the relevant info)

## Workflow
[View workflow diagram](assets/workflow-diagram.png)

## Demo
[View chat demo](assets/chat-demo.png)

## Knowledge base
I made a simple spreadsheet with categories like Terminal Info, Baggage Rules, Airport Services, and Transport & Parking, and connected it to the workflow so the AI Agent can pull answers from it.

## How to run this yourself
1. Self-host n8n using Docker:
   `docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n`
2. Import `workflow.json` into your n8n instance
3. Get your own Gemini API key from [Google AI Studio](https://aistudio.google.com/app/apikey)
4. Set up your own Google Sheets OAuth credentials via [Google Cloud Console](https://console.cloud.google.com/)
5. Connect it to your own knowledge base spreadsheet

## Certification
I completed "Automate Everything With n8n" (LetsUpgrade, in collaboration with NSDC) as part of learning n8n for this project.

[View certificate](assets/n8n-certificate.jpeg)
