# Block 5: Connect HubSpot (Optional)

## EXPLAIN

HubSpot is **optional** — only do this block if your team uses HubSpot for CRM, marketing, or sales.

### Step-by-Step Guide

#### Step 1: Open Connectors

📱 **Desktop App:**
1. Click the **Settings** icon (gear icon)
2. Go to **Connectors** → **Browse Connectors**

#### Step 2: Find and Connect HubSpot

📱 **Desktop App:**
1. Search for or scroll to **HubSpot**
2. Click **Connect**
3. A browser window will open for HubSpot authorization:
   - Select **"Swingvy (9014681)"** as the account
   - Select **all optional scopes**
   - Click the checkbox to activate the "Connect app" button
   - Click **"Connect app"**

#### Step 3: Test it!

📱 **Desktop App:** Try these queries:

```
Show me my recent HubSpot contacts
List deals in the pipeline
```

### What You Can Do

| HubSpot Area | Example queries |
|--------------|----------------|
| **CRM** | "Find contact John Smith", "Show recent deals" |
| **Contacts** | "List contacts added this week", "Search for company X" |
| **Deals** | "What deals are in the pipeline?", "Show deals closing this month" |
| **Marketing** | "Show recent HubSpot campaigns", "What's the open rate on our last campaign?" |

### Troubleshooting

| Problem | Solution |
|---------|----------|
| HubSpot not in Connectors | Make sure Claude Code is enabled (Block 1) |
| Auth page won't open | Copy the URL and paste in your browser |
| "Unauthorized" | Try disconnecting and reconnecting via Settings → Connectors |
| Can't access data | Your HubSpot role may not have API permissions — check with admin |
| Wrong account selected | Make sure to select "Swingvy (9014681)" during OAuth |

## EXECUTE

Follow the 3 steps above:

1. 📱 **Settings** → **Connectors** → **Browse Connectors**
2. 📱 Find **HubSpot** → Click **Connect** → Select Swingvy (9014681) → Grant all scopes → Connect app
3. 📱 Try `Show me my recent HubSpot contacts`

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "When connecting HubSpot, which account should you select?",
    "header": "HubSpot Quiz",
    "options": [
      {"label": "Swingvy (9014681)", "description": ""},
      {"label": "Your personal HubSpot account", "description": ""},
      {"label": "Any account — it doesn't matter", "description": ""},
      {"label": "You don't need to select an account", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Swingvy (9014681)"

If correct: "Exactly! Make sure to select the Swingvy company account during authorization so Claude has access to our shared CRM data."
If incorrect: "When connecting HubSpot, always select **Swingvy (9014681)** — that's our company account. Selecting a personal account would only give Claude access to your personal HubSpot data, not the team's CRM."
