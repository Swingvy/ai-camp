# Block 0: Why Connect Tools?

## EXPLAIN

By default, Claude Code can only work with **files on your computer**. But your real work lives in Slack, Jira, Google Calendar, HubSpot, and more. Today we'll give Claude access to those tools.

### The Before & After

```
Before connecting tools:
  You ←→ Claude Code ←→ Files on your computer

After connecting tools:
  You ←→ Claude Code ←→ Slack
                      ←→ Jira & Confluence
                      ←→ Google Calendar, Drive, Docs
                      ←→ HubSpot
                      ←→ (and more)
```

### Real Examples

| What you say | What Claude does |
|--------------|------------------|
| "What's happening in #swingvy_general?" | Reads your Slack channel and summarizes |
| "What are my open Jira issues?" | Fetches your assigned Jira issues |
| "What's my upcoming schedule?" | Checks your Google Calendar |
| "Show me recent HubSpot contacts" | Queries your CRM |

### How Do Connections Work?

Claude Desktop App has a built-in **Connectors** feature that makes connecting tools simple:

1. Open **Settings** (gear icon) in your Claude Desktop App
2. Go to **Connectors** → **Browse Connectors**
3. Find the tool you want → Click **Connect**
4. Authorize access in the browser popup

That's it! No Terminal commands needed. The Desktop App handles everything for you.

### Today's Plan

We'll connect **4 tools** step by step:

| Step | Tool | Difficulty |
|------|------|------------|
| 1 | Slack | Easy |
| 2 | Jira & Confluence | Easy |
| 3 | Google Workspace (Calendar, Drive, Docs, Gmail) | Easy |
| 4 | HubSpot (Optional) | Easy |

## EXECUTE

Let's take a look at the Connectors screen.

📱 **Desktop App:**
1. Click the **Settings** icon (gear icon) in your Claude Desktop App
2. Go to **Connectors**
3. Browse what's available

If you see a list of connectors, you're in the right place! We'll connect your first tool in the next block.

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What does connecting tools do for Claude Code?",
    "header": "Concept Quiz",
    "options": [
      {"label": "Makes Claude Code faster", "description": ""},
      {"label": "Lets Claude access external tools like Slack, Jira, and Google Calendar", "description": ""},
      {"label": "Adds a graphical interface to Claude Code", "description": ""},
      {"label": "Replaces your work tools with Claude", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Lets Claude access external tools like Slack, Jira, and Google Calendar"

If correct: "Exactly! Connecting tools gives Claude arms that can reach into Slack, Jira, Google Calendar, and more. Without connections, Claude only sees your local files. With them, Claude becomes your work assistant across all your tools."
If incorrect: "Connecting tools lets Claude access your external work tools — Slack, Jira, Google Calendar, HubSpot, etc. Think of each connection as a bridge between Claude and one of your tools. Claude doesn't replace them — it connects to them."
