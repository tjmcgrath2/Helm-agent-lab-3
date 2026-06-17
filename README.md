# Helm-agent-lab-3
AI project management agent for assisting with organization and prioritization of tasks. 
Helm — AI Project Management Assistant

What it is

Helm is a standalone, single file web application that acts as an AI project management assistant. A user loads project task data, and Helm performs three project management functions on demand:


Status Report: an executive ready summary grouping tasks by status, with accomplishments, risks, blockers, and recommended next actions.
Prioritize Tasks: a ranked table scoring each task High, Medium, or Low based on due date, dependencies, and business impact, plus a "focus this week" callout.
Timeline Update: an on track or at risk assessment of each task against today's date, flagging overdue items and proposing a revised sequence for dependencies.


It is one HTML file with no build step, no server, and no installation. It runs in any modern browser.

How it works

The app sends a system prompt plus a task specific prompt (built from the user's data, the current date, and optional context) directly to a large language model API. The model returns Markdown, which Helm renders as formatted tables, priority badges, and sections. The architecture is a client side prompt chaining flow: one structured prompt per function, each engineered for a specific PM output rather than open chat.

Tools and technologies used


HTML, CSS, and vanilla JavaScript (single file, no dependencies)
A large language model API of your choice: OpenAI (ChatGPT), Google Gemini, or Anthropic (Claude)
Browser localStorage to persist the API key and project data between sessions
Prompt engineering: a fixed system role plus three task specific prompt templates


How to run it


Double click pm-assistant.html to open it in your browser. No install needed.
Click Settings in the top right.
Choose a provider, optionally set a model name, and paste your API key. Click Save.
Click Load sample project, or paste your own task list into the Project Data box.
Click Status Report, Prioritize Tasks, or Timeline Update.


To share a testable link for the lab, upload the single HTML file to any static host (GitHub Pages, Netlify drop, or Google Sites file embed). No backend is required.

Credentials required

You need one API key from any of the supported providers. The key is stored only in your browser and is sent directly to the provider you chose. It never passes through any other server.


OpenAI: create a key at platform.openai.com under API keys. Default model gpt-4o-mini.
Google Gemini: create a key at aistudio.google.com. Default model gemini-1.5-flash.
Anthropic: create a key at console.anthropic.com. Default model claude-3-5-sonnet-20241022.


The cheapest option for grading is OpenAI gpt-4o-mini or Gemini gemini-1.5-flash. A full demo run of all three functions costs a fraction of a cent.

Expected data format

Helm works best with one task per line including task name, owner, status, due date, and notes. CSV with a header row or freeform text both work. The Load sample project button populates a realistic manufacturing project so you can demo immediately.

