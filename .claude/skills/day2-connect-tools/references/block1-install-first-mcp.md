# Block 1: Install Your First MCP Server

## EXPLAIN

Let's connect your first tool. The process is always the same:

```
claude mcp add <name> -- <command to run the server>
```

That's it. One command to connect one tool.

### Example: File System MCP (simplest, no auth needed)

```bash
claude mcp add filesystem -- npx -y @anthropic-ai/mcp-filesystem
```

This lets Claude safely read and write files in specific directories.

### Example: Slack MCP

```bash
claude mcp add slack -- npx -y @anthropic-ai/mcp-slack
```

This requires a Slack token. Claude will guide you through getting one, or your IT admin may have prepared it.

### Example: Google Drive MCP

```bash
claude mcp add gdrive -- npx -y @anthropic-ai/mcp-gdrive
```

Requires Google OAuth setup. Follow the browser prompt to authorize.

### After Installing

Restart Claude Code (exit and `claude` again), then test:

```
You: "Use the filesystem MCP to list files in my Documents folder"
You: "Check my latest Slack messages in #general"
You: "List my recent Google Drive files"
```

### If Something Goes Wrong

| Problem | Solution |
|---------|----------|
| "Server not found" | Check the package name — typos are common |
| "Auth failed" | Re-run auth: the server will prompt you |
| "Connection refused" | Restart Claude Code after adding MCP |
| "Permission denied" | Check with IT — some tools need admin approval |

Useful debug commands:
```bash
claude mcp list          # See what's connected
claude mcp remove <name> # Remove a broken connection
```

## EXECUTE

Install your first MCP server. Pick the one most relevant to your work:

**Option A: Filesystem (easiest, no setup)**
```bash
claude mcp add filesystem -- npx -y @anthropic-ai/mcp-filesystem
```

**Option B: Slack (if you use Slack daily)**
```bash
claude mcp add slack -- npx -y @anthropic-ai/mcp-slack
```

**Option C: Google Drive (if you use Google Workspace)**
```bash
claude mcp add gdrive -- npx -y @anthropic-ai/mcp-gdrive
```

After installing:
1. Exit Claude Code (`/exit`)
2. Restart (`claude`)
3. Test it with a simple query related to that tool

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What command adds a new MCP server to Claude Code?",
    "header": "MCP Install Quiz",
    "options": [
      {"label": "claude install mcp slack", "description": ""},
      {"label": "npm install slack-mcp", "description": ""},
      {"label": "claude mcp add slack -- npx -y @anthropic-ai/mcp-slack", "description": ""},
      {"label": "mcp connect slack", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: `claude mcp add slack -- npx -y @anthropic-ai/mcp-slack`

If correct: "Right! The pattern is always `claude mcp add <name> -- <command>`. The name is what YOU call it, the command is what runs the server."
If incorrect: "The pattern is: `claude mcp add <name> -- <command>`. You pick the name (like 'slack'), and the command runs the MCP server package. After adding, restart Claude Code to activate it."
