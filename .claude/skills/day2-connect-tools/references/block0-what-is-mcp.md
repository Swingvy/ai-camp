# Block 0: What is MCP?

## EXPLAIN

MCP stands for **Model Context Protocol**. Think of it as **plugins for Claude Code**.

Without MCP, Claude can only work with files on your computer. With MCP, Claude can reach into your work tools — Slack, Notion, Google Drive, Linear, and more.

### The Mental Model

```
Before MCP:
  You ←→ Claude Code ←→ Files on your computer

After MCP:
  You ←→ Claude Code ←→ Slack
                      ←→ Google Drive
                      ←→ Notion
                      ←→ Calendar
                      ←→ (any tool with an MCP server)
```

### Real Examples

| What you say | What Claude does (with MCP) |
|--------------|-----------------------------|
| "What's happening in #product-feedback?" | Reads your Slack channel and summarizes |
| "Create a Google Doc with today's meeting notes" | Creates an actual Google Doc in your Drive |
| "What are my open tasks in Linear?" | Fetches your assigned issues |
| "Block my calendar tomorrow 2-3pm for deep work" | Creates a calendar event |

### How It Works (Simple Version)

1. You install an **MCP server** — a small connector for a specific tool
2. The MCP server handles authentication (logging into that tool)
3. Claude Code can now talk to that tool through the server
4. You just ask Claude in plain language — the MCP server translates

### What's Available?

There are MCP servers for most popular work tools. You don't need to build them — they already exist. You just install and connect.

## EXECUTE

Let's see what MCP connections you already have (probably none yet, and that's fine):

```bash
# Outside Claude Code, in your terminal:
claude mcp list
```

If it shows nothing, that's expected! We'll install your first one in the next block.

Now, make a list of the tools you use most at work. We'll connect them:

```
My daily tools:
1. _______________
2. _______________
3. _______________
```

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What does MCP do for Claude Code?",
    "header": "MCP Concept Quiz",
    "options": [
      {"label": "Makes Claude Code faster", "description": ""},
      {"label": "Connects Claude Code to external tools like Slack, Notion, and Google Drive", "description": ""},
      {"label": "Adds a graphical interface to Claude Code", "description": ""},
      {"label": "Translates Claude Code to different languages", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Connects Claude Code to external tools like Slack, Notion, and Google Drive"

If correct: "Exactly! MCP is like giving Claude Code arms that can reach into your work tools. Without it, Claude only sees your local files. With it, Claude can read Slack, create Google Docs, check your calendar, and more."
If incorrect: "MCP connects Claude Code to your external work tools. Think of it as plugins — each MCP server is a bridge between Claude and one of your tools (Slack, Notion, Google Drive, etc.)."
