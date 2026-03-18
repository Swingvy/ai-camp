# Block 2: Connect Slack

## EXPLAIN

Let's connect your first tool — **Slack**. This is the easiest one because it's available right in the Connectors menu.

### Step-by-Step Guide

#### Step 1: Open Connectors

📱 **Desktop App:**
1. Click the **Settings** icon (gear icon)
2. Go to **Connectors** → **Browse Connectors**

#### Step 2: Find and Connect Slack

📱 **Desktop App:**
1. Search for or scroll to **Slack**
2. Click **Connect**
3. A browser window will open — log in to your Slack workspace and authorize access

#### Step 3: Test it!

📱 **Desktop App:** Try this query:

```
What's the most recent message in #swingvy_general?
```

If Claude reads your Slack channel and shows you the message — congratulations, Slack is connected!

### What You Can Do with Slack

| Action | Example query |
|--------|--------------|
| Read channels | "What's happening in #engineering?" |
| Search messages | "Find messages about the launch in #marketing" |
| Send messages | "Send a message to #team-updates saying..." |
| Summarize | "Summarize the last week of #product-feedback" |

### Troubleshooting

| Problem | Solution |
|---------|----------|
| Slack not in Connectors list | Make sure Claude Code is enabled (Block 1) |
| Authentication page won't open | Copy the URL and paste in your browser |
| "Channel not found" | Check the exact channel name (case-sensitive) |
| Can't read messages | You may need to be a member of that channel |

## EXECUTE

Follow the 3 steps above:

1. 📱 **Settings** → **Connectors** → **Browse Connectors**
2. 📱 Find **Slack** → Click **Connect** → Authorize in browser
3. 📱 Try `What's the most recent message in #swingvy_general?`

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "How do you connect Slack to Claude?",
    "header": "Slack Quiz",
    "options": [
      {"label": "Settings → Connectors → Browse Connectors → Slack → Connect", "description": ""},
      {"label": "Type a command in Terminal", "description": ""},
      {"label": "Download a separate Slack plugin", "description": ""},
      {"label": "Copy-paste an API key into Claude", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Settings → Connectors → Browse Connectors → Slack → Connect"

If correct: "Right! All tool connections go through Settings → Connectors in the Desktop App. No Terminal commands needed — just find the tool and click Connect. Easy!"
If incorrect: "Slack (and all other tools) connect through **Settings → Connectors → Browse Connectors** in the Desktop App. Just find Slack, click Connect, and authorize. No Terminal needed!"
