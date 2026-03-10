# Block 2: Popular MCP Servers

## EXPLAIN

Here's a catalog of MCP servers organized by the tools you likely use. Find your tools and install the matching servers.

### Communication

| Tool | Install command | What you can do |
|------|----------------|-----------------|
| Slack | `claude mcp add slack -- npx -y @anthropic-ai/mcp-slack` | Read channels, send messages, search history |
| Email (Gmail) | `claude mcp add gmail -- npx -y @anthropic-ai/mcp-gmail` | Read, draft, send emails |

### Documents & Knowledge

| Tool | Install command | What you can do |
|------|----------------|-----------------|
| Google Drive | `claude mcp add gdrive -- npx -y @anthropic-ai/mcp-gdrive` | Read/create Docs, Sheets, Slides |
| Notion | `claude mcp add notion -- npx -y @anthropic-ai/mcp-notion` | Read/update pages, databases |
| Confluence | `claude mcp add confluence -- npx -y @anthropic-ai/mcp-confluence` | Read/search wiki pages |

### Project Management

| Tool | Install command | What you can do |
|------|----------------|-----------------|
| Linear | `claude mcp add linear -- npx -y @anthropic-ai/mcp-linear` | Issues, projects, sprints |
| Jira | `claude mcp add jira -- npx -y @anthropic-ai/mcp-jira` | Issues, boards, sprints |
| GitHub | `claude mcp add github -- npx -y @anthropic-ai/mcp-github` | Issues, PRs, repos |

### Other

| Tool | Install command | What you can do |
|------|----------------|-----------------|
| Calendar | `claude mcp add calendar -- npx -y @anthropic-ai/mcp-google-calendar` | View/create events |
| Filesystem | `claude mcp add filesystem -- npx -y @anthropic-ai/mcp-filesystem` | Safe file access |
| Web/Browser | `claude mcp add web -- npx -y @anthropic-ai/mcp-web` | Fetch web pages |

### Finding More Servers

MCP servers are being created constantly. To find one for your tool:
- Search: "MCP server [tool name]"
- Check: mcp.anthropic.com for official listings
- Ask Claude: "Is there an MCP server for [tool]?"

### How Many Should You Install?

Start with 2-3 that you use DAILY. You can always add more later. The most powerful combinations are when you connect tools that you currently copy-paste between:

```
Slack + Google Sheets = "Summarize feedback from Slack into a spreadsheet"
Linear + Slack = "Post sprint status to #team-updates"
Google Drive + Notion = "Sync meeting notes from Docs to Notion"
```

## EXECUTE

1. Look at the tables above and identify 2 tools you use every day
2. Install the MCP servers for those tools
3. Restart Claude Code
4. Test each one with a simple query:

```
"Show me my recent messages from Slack #general"
"List my Google Drive files from this week"
"What are my open Linear issues?"
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
