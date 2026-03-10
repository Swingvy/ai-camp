# Block 4: MCP Troubleshooting

## EXPLAIN

MCP servers can be finicky. Here's how to diagnose and fix the most common issues.

### Diagnostic Commands

```bash
# See all connected MCP servers
claude mcp list

# Remove a broken server
claude mcp remove <name>

# Re-add with correct settings
claude mcp add <name> -- <command>
```

### Common Problems & Solutions

**Problem 1: "Server not starting"**
```
Symptom: Claude says it can't connect to the MCP server
```
Solutions:
1. Restart Claude Code (`/exit` then `claude`)
2. Check if the package name is correct (typos are #1 cause)
3. Try reinstalling: `claude mcp remove <name>` then `claude mcp add` again
4. Check Node.js is working: `node --version`

**Problem 2: "Authentication failed"**
```
Symptom: Server starts but can't access your data
```
Solutions:
1. The auth token may have expired — re-authenticate
2. For Slack: generate a new token in your Slack workspace settings
3. For Google: re-run the OAuth flow (browser will open)
4. Ask IT if the API is restricted in your organization

**Problem 3: "Permission denied"**
```
Symptom: Claude can read but not write, or can't access certain channels/folders
```
Solutions:
1. Check the permissions/scopes of your auth token
2. For Slack: ensure the bot has access to the channels you need
3. For Google Drive: check sharing settings on the files/folders
4. Some tools require admin approval for API access

**Problem 4: "Timeout" or "No response"**
```
Symptom: Claude hangs when trying to use MCP
```
Solutions:
1. Your internet connection may be slow — try again
2. The external tool's API might be down — try later
3. The query might be too large — narrow it (e.g., "last 3 days" instead of "last year")

### The "Nuclear Option" — Start Fresh

If nothing works:
```bash
# Remove the problematic server
claude mcp remove <name>

# Clear any cached credentials (location varies by server)

# Re-add from scratch
claude mcp add <name> -- <command>

# Restart Claude
/exit
claude
```

### When to Ask for Help

Ask IT or your instructor when:
- Your organization blocks API access
- You need admin-level tokens
- OAuth keeps failing after multiple attempts
- A specific tool is behind a VPN

## EXECUTE

Let's health-check your MCP connections:

1. Run `claude mcp list` to see all your servers
2. For each server, try a simple read query:
   - Slack: "What's the most recent message in #general?"
   - Google Drive: "List my 3 most recent files"
   - Notion: "Show me my recent pages"
   - Linear: "What issues are assigned to me?"
3. If any fail, use the troubleshooting guide above to fix it
4. If you get stuck, pair up with a neighbor or ask the instructor

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Your MCP Slack server was working yesterday but not today. What's the FIRST thing to try?",
    "header": "Troubleshooting Quiz",
    "options": [
      {"label": "Reinstall Claude Code completely", "description": ""},
      {"label": "Restart Claude Code (/exit then claude)", "description": ""},
      {"label": "Delete everything and start over", "description": ""},
      {"label": "Switch to a different computer", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Restart Claude Code (/exit then claude)"

If correct: "Yes! The classic 'turn it off and on again' works surprisingly often. MCP servers reconnect on restart. If that doesn't work, then check auth tokens, then try removing and re-adding the server."
If incorrect: "Always start simple. Restart Claude Code first (`/exit` then `claude`). Most MCP issues are resolved by a restart. If that doesn't fix it, check auth tokens next, then try removing and re-adding the server. No need to reinstall everything!"
