---
name: day2-connect-tools
description: "Internal Camp Day 2: Connect your work tools via MCP. Covers MCP concepts, installing servers, cross-tool queries, and troubleshooting. Use for \"Day 2\", \"MCP\", \"connect tools\", \"Slack\", \"Notion\", \"Google Drive\"."
---

# Day 2: Connect Your Tools (MCP)

This skill teaches participants to connect their daily work tools (Slack, Notion, Google Drive, etc.) to Claude Code using MCP, and run cross-tool queries.

---

## STOP PROTOCOL

> Same 2-turn protocol as Day 1. Never violate.

### Each block = 2 turns

```
Phase A: Explain + Execute instructions → STOP (no questions)
Phase B: Quiz + feedback → next block
```

Phase A must end with:
```
---
👆 Try this yourself now.
When you're done, type "done" or "next" to continue.
```

---

## Block Map

| Block | File | Topic |
|-------|------|-------|
| 0 | `references/block0-what-is-mcp.md` | What is MCP + mental model |
| 1 | `references/block1-install-first-mcp.md` | Install your first MCP server |
| 2 | `references/block2-popular-servers.md` | Popular MCP servers by tool |
| 3 | `references/block3-cross-tool.md` | Cross-tool queries |
| 4 | `references/block4-troubleshooting.md` | Troubleshooting + debugging |
| 5 | `references/block5-homework.md` | Homework: connect 2 more tools |

---

## Interaction Rules

- One block at a time
- Before Block 1, ask what tools the participant uses daily (Slack, Notion, Google Drive, Linear, Jira, Figma, Salesforce, HubSpot, etc.)
- Tailor all examples to the participant's actual tools
- For MCP issues, check: auth tokens, permissions, server startup
- Helpful commands to reference: `claude mcp list`, `claude mcp remove`
- Tone: patient, encouraging — MCP setup can be frustrating

---

## Start

```
AskUserQuestion({
  "questions": [{
    "question": "Where would you like to start?",
    "header": "Day 2: Connect Your Tools",
    "options": [
      {"label": "Block 0: What is MCP?", "description": "The mental model — plugins for Claude Code"},
      {"label": "Block 1: First MCP Server", "description": "Install and test your first connection"},
      {"label": "Block 2: Popular Servers", "description": "Find servers for your specific tools"},
      {"label": "Block 3: Cross-tool Queries", "description": "Query across 2+ tools at once"},
      {"label": "Block 4: Troubleshooting", "description": "Fix common MCP issues"},
      {"label": "Block 5: Homework", "description": "Connect 2 more tools on your own"}
    ],
    "multiSelect": false
  }]
})
```
