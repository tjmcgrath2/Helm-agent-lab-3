# Helm — AI Project Management Assistant

Helm is a standalone, single file web app that acts as an AI project management assistant. Load your project tasks, and Helm performs three project management functions on demand: status reporting, task prioritization, and timeline updates.

Built as a course project for an AI in project management lab. It improves on an earlier n8n and Pinecone lookup agent by being a self contained, dependency free product that runs in any browser with no server and no build step.

## Live demo

**[Open the assistant](https://YOUR-USERNAME.github.io/REPO-NAME/pm-assistant.html)**

The demo opens in Offline Demo mode, so you can click **Load sample project** and run all three functions immediately, no API key required.

## What it does

- **Status Report**: an executive ready summary grouping tasks by status, with accomplishments, risks, blockers, and recommended next actions, each tied to an owner.
- **Prioritize Tasks**: a ranked table scoring each task High, Medium, or Low based on due date, dependencies, and business impact, plus a focus this week callout.
- **Timeline Update**: an on track or at risk assessment of each task against today's date, flagging overdue items and proposing a revised sequence for dependencies.

## How it works

Helm sends a system prompt plus a task specific prompt, built from your data, the current date, and optional context, directly to a large language model. The model returns Markdown, which Helm renders as formatted tables, priority badges, and sections. This is a client side prompt chaining flow: one engineered prompt per function rather than open chat.

## Running it

1. Open the [live demo](https://YOUR-USERNAME.github.io/REPO-NAME/pm-assistant.html), or download `pm-assistant.html` and double click it.
2. Click **Load sample project**, or paste your own task list (task name, owner, status, due date, and notes).
3. Run **Status Report**, **Prioritize Tasks**, or **Timeline Update**. This works instantly in Offline Demo mode.
4. For live AI on your own data, open **Settings**, choose a provider, paste your API key, and Save.

## Modes

- **Offline Demo** (default): returns a realistic pre built analysis of the sample project with no key. Best for sharing and grading.
- **Live**: runs the same functions against a real model on whatever data you provide.

## Supported providers (live mode)

| Provider | Default model | Get a key |
|----------|---------------|-----------|
| OpenAI (ChatGPT) | gpt-4o-mini | platform.openai.com |
| Google Gemini | gemini-1.5-flash | aistudio.google.com |
| Anthropic (Claude) | claude-3-5-sonnet-20241022 | console.anthropic.com |

Your API key is stored only in your browser and sent directly to the provider you choose. It never passes through any other server, and it is never stored in this repository.

## Tech

HTML, CSS, and vanilla JavaScript in a single file. No dependencies, no build step, no backend.
