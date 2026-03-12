# Block 2: Popular MCP Servers

## EXPLAIN

Here's a catalog of MCP servers organized by the tools you likely use. Find your tools and install the matching servers.

### Communication

| Tool | Install method | What you can do |
|------|----------------|-----------------|
| Slack | `/install slack` | Read channels, send messages, search history |
| Gmail | `/install gmail` | Read, draft, send emails |

### Documents & Storage

| Tool | Install method | What you can do |
|------|----------------|-----------------|
| Google Drive | gws CLI (see setup below) | Read/create Docs, Sheets, Slides |
| Google Docs | Part of gws CLI setup | Create and edit documents |
| Dropbox | `claude mcp add dropbox -- npx -y @anthropic-ai/mcp-dropbox` | File storage and sharing |

### Google Workspace (gws CLI Setup)

Many Google tools are accessed through a single CLI called **gws**. Here's how to set it up:

1. **Install gws**: `npm install -g @anthropic-ai/gws`
2. **Authenticate**: `gws auth login`
3. Follow the browser prompt to authorize with your Google account
4. **Test**: `gws drive list` to verify connection
5. **Connect to Claude**: `claude mcp add gws -- gws mcp`

Once connected, Claude can access Google Drive, Google Docs, Google Sheets, Google Calendar, and Google Meet — all through this single setup.

### Calendar & Meetings

| Tool | Install method | What you can do |
|------|----------------|-----------------|
| Google Calendar | Part of gws CLI setup | View/create events |
| Google Meet | Part of gws CLI setup | View meeting details |

### Project Management

| Tool | Install method | What you can do |
|------|----------------|-----------------|
| Jira | `claude mcp add jira -- npx -y @anthropic-ai/mcp-jira` | Issues, boards, sprints |
| Confluence | `claude mcp add confluence -- npx -y @anthropic-ai/mcp-confluence` | Read/search wiki pages |

### CRM & Marketing

| Tool | Install method | What you can do |
|------|----------------|-----------------|
| HubSpot | `claude mcp add hubspot -- npx -y @anthropic-ai/mcp-hubspot` | CRM, contacts, deals, marketing |

### Finding More Servers

MCP servers are being created constantly. To find one for your tool:
- Search: "MCP server [tool name]"
- Check: mcp.anthropic.com for official listings
- Ask Claude: "Is there an MCP server for [tool]?"

### How Many Should You Install?

Start with 2-3 that you use DAILY. You can always add more later. The most powerful combinations are when you connect tools that you currently copy-paste between:

```
Slack + Google Docs = "Summarize feedback from Slack into a Google Doc"
Jira + Slack = "Post sprint status to #team-updates"
Google Drive + Confluence = "Sync meeting notes from Docs to Confluence"
```

## EXECUTE

1. Look at the tables above and identify 2 tools you use every day
2. Install the MCP servers for those tools
3. Restart Claude Code
4. Test each one with a simple query:

```
"Show me my recent messages from Slack #general"
"List my Google Drive files from this week"
"What are my open Jira issues?"
```

If you don't see your tool listed, ask me! I can help find or suggest an MCP server for it.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "You use Slack and Google Sheets daily, and you often copy data from Slack into a spreadsheet. How does MCP help?",
    "header": "Tool Connection Quiz",
    "options": [
      {"label": "MCP can only connect one tool at a time", "description": ""},
      {"label": "You still need to copy-paste, but Claude helps format it", "description": ""},
      {"label": "Claude can read Slack AND write to Google Sheets — no more copy-paste", "description": ""},
      {"label": "MCP replaces Slack and Google Sheets with Claude", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Claude can read Slack AND write to Google Sheets — no more copy-paste"

If correct: "That's the magic! With both MCP servers connected, you can say 'Collect all feature requests from #product-feedback this week and add them to my tracking spreadsheet.' Claude reads one tool and writes to another. No more manual copying."
If incorrect: "When you connect multiple MCP servers, Claude can read from one tool and write to another in a single conversation. So instead of manually copying Slack messages into a spreadsheet, you just ask Claude to do it. That's the real power of MCP."
