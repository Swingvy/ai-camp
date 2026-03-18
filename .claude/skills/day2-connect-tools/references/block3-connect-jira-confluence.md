# Block 3: Connect Jira & Confluence

## EXPLAIN

Now let's connect **Jira and Confluence** — both are Atlassian products, so one connection gives you access to both!

### Step-by-Step Guide

#### Step 1: Open Connectors

📱 **Desktop App:**
1. Click the **Settings** icon (gear icon)
2. Go to **Connectors** → **Browse Connectors**

#### Step 2: Find and Connect Atlassian

📱 **Desktop App:**
1. Search for or scroll to **Atlassian** (this covers both Jira and Confluence)
2. Click **Connect**
3. A browser window will open — log in to your Atlassian account and authorize access

#### Step 3: Test it!

📱 **Desktop App:** Try these queries:

```
What are my open Jira issues?
Search Confluence for "onboarding guide"
```

If Claude shows your Jira issues or finds Confluence pages — Atlassian is connected!

### What You Can Do

| Tool | Example queries |
|------|----------------|
| **Jira** | "What issues are assigned to me?", "Show my sprint board", "Create a new ticket" |
| **Confluence** | "Find the onboarding doc", "Read page ID 12345", "Search for meeting notes" |

### Troubleshooting

| Problem | Solution |
|---------|----------|
| Atlassian not in Connectors | Make sure Claude Code is enabled (Block 1) |
| Auth fails | Make sure you're logging into the right Atlassian workspace |
| "No permission" | Ask your admin if API access is enabled |
| Can't find pages | Try using the page ID instead of the title |

## EXECUTE

Follow the 3 steps above:

1. 📱 **Settings** → **Connectors** → **Browse Connectors**
2. 📱 Find **Atlassian** → Click **Connect** → Authorize in browser
3. 📱 Try `What are my open Jira issues?`

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "How many connectors do you need for Jira AND Confluence?",
    "header": "Atlassian Quiz",
    "options": [
      {"label": "One — the Atlassian connector covers both", "description": ""},
      {"label": "Two — one for Jira and one for Confluence", "description": ""},
      {"label": "Three — Jira, Confluence, and Atlassian separately", "description": ""},
      {"label": "None — they're already built into Claude", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "One — the Atlassian connector covers both"

If correct: "Correct! One Atlassian connector gives you both Jira and Confluence. That's the nice thing about Atlassian products — they share the same connection."
If incorrect: "You only need **one** connector — the Atlassian connector covers both Jira and Confluence. Since they're both Atlassian products, a single connection handles both!"
