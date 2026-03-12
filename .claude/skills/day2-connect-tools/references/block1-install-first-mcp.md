# Block 1: Install Your First MCP Server

## EXPLAIN

Let's connect your first tool. We'll start with **Slack** — it's the most commonly used and has a streamlined install process.

### Installing Slack MCP

The simplest way to install Slack is with the plugin install command:

```bash
/install slack
```

That's it! Claude Code will handle the setup and guide you through authenticating with your Slack workspace.

### The General Pattern

For other tools, you'll use this pattern:

```
claude mcp add <name> -- <command to run the server>
```

But for Slack, `/install slack` does everything for you.

### After Installing

Restart Claude Code (exit and `claude` again), then test:

```
You: "Check my latest Slack messages in #general"
You: "What's the most recent message in #random?"
You: "Search Slack for messages about the weekly standup"
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

Install Slack as your first MCP server:

```bash
/install slack
```

After installing:
1. Exit Claude Code (`/exit`)
2. Restart (`claude`)
3. Test it: "What's the most recent message in #general?"

If you don't use Slack, no worries — pick a tool from Block 2 instead.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What's the simplest way to install Slack MCP in Claude Code?",
    "header": "MCP Install Quiz",
    "options": [
      {"label": "claude install mcp slack", "description": ""},
      {"label": "npm install slack-mcp", "description": ""},
      {"label": "/install slack", "description": ""},
      {"label": "mcp connect slack", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: `/install slack`

If correct: "Right! `/install slack` is the quickest way to get Slack connected. For other tools, you'll use `claude mcp add <name> -- <command>`. After installing, always restart Claude Code to activate the new connection."
If incorrect: "The simplest way is `/install slack` — it handles all the setup for you. For other MCP servers, the general pattern is `claude mcp add <name> -- <command>`. After adding any MCP server, restart Claude Code to activate it."
