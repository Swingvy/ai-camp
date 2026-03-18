# Block 4: Connect Google Workspace

## EXPLAIN

Google Workspace includes **Calendar, Drive, Docs, Sheets, and Gmail**. You can connect each one through the Connectors menu — the same way you connected Slack and Atlassian.

### Step-by-Step Guide

#### Step 1: Open Connectors

📱 **Desktop App:**
1. Click the **Settings** icon (gear icon)
2. Go to **Connectors** → **Browse Connectors**

#### Step 2: Connect Google Tools

📱 **Desktop App:**

You'll see several Google connectors available. Connect the ones you use:

| Connector | What it enables |
|-----------|----------------|
| **Google Calendar** | View your schedule, create events, check availability |
| **Google Drive** | Browse files, search documents |
| **Google Docs** | Read and create documents |
| **Google Sheets** | Read and edit spreadsheets |
| **Gmail** | Read emails, draft replies, search inbox |

For each one:
1. Find the connector in the list
2. Click **Connect**
3. Authorize with your Google account in the browser popup

> **Tip:** Start with **Google Calendar** — it's the quickest to verify since you can immediately ask about your schedule.

#### Step 3: Test it!

📱 **Desktop App:** Try these queries:

```
What's my schedule for today?
Show my recent Google Drive files
Do I have any unread emails?
```

If Claude shows your calendar events, files, or emails — Google Workspace is connected!

### What You Can Do

| Google Tool | Example queries |
|-------------|----------------|
| **Calendar** | "What's my schedule tomorrow?", "Block 2-3pm for deep work" |
| **Drive** | "List my recent files", "Find the Q1 report" |
| **Docs** | "Create a meeting notes document", "Read the onboarding doc" |
| **Sheets** | "Open my tracking spreadsheet", "Add a row to the budget sheet" |
| **Gmail** | "Show my unread emails", "Draft a reply to..." |

### Troubleshooting

| Problem | Solution |
|---------|----------|
| Google connectors not showing | Make sure Claude Code is enabled (Block 1) |
| Auth fails | Make sure you're using your work Google account |
| "Permission denied" | You may need to authorize additional scopes — try disconnecting and reconnecting |
| Can't find files | Be specific with file names or try searching by keyword |

## EXECUTE

Follow the steps above:

1. 📱 **Settings** → **Connectors** → **Browse Connectors**
2. 📱 Connect at least **Google Calendar** and **one other** Google tool
3. 📱 Try `What's my schedule for today?`

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "How do you connect Google Workspace tools to Claude?",
    "header": "Google Workspace Quiz",
    "options": [
      {"label": "Settings → Connectors → Browse Connectors → find each Google tool → Connect", "description": ""},
      {"label": "Install a CLI tool in Terminal", "description": ""},
      {"label": "Copy an API key from Google Cloud Console", "description": ""},
      {"label": "Google tools are automatically connected", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Settings → Connectors → Browse Connectors → find each Google tool → Connect"

If correct: "Exactly! Just like Slack and Atlassian, Google tools connect through Settings → Connectors. Find each Google tool you want, click Connect, and authorize. Same simple process for everything!"
If incorrect: "Google Workspace tools connect the same way as everything else — through **Settings → Connectors → Browse Connectors**. Find Google Calendar, Gmail, Drive, etc., click Connect, and authorize with your Google account. No CLI tools needed!"
