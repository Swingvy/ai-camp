# Block 1: Install Claude Code in Claude Desktop App

## EXPLAIN

Before we connect any tools, we need **Claude Code** running. Claude Code is the powerful engine inside your Claude Desktop App that can connect to external tools, run commands, and automate your work.

### What is Claude Code?

In Day 1, you used the **Claude Desktop App** to have conversations. Claude Code is a **feature inside the Desktop App** that gives you access to powerful capabilities like:

- **Connectors** — connect to Slack, Jira, Google Calendar, HubSpot, and more
- **Skills** — run custom commands and automations
- **File access** — read and write files on your computer
- **Terminal commands** — run commands when needed

### How to Enable Claude Code in Desktop App

#### Step 1: Open Claude Desktop App

Launch the Claude Desktop App you installed on Day 1.

#### Step 2: Enable Claude Code

In the Claude Desktop App:
1. Look for the **Claude Code** toggle or terminal icon in the **top-center** area of the window
2. Click it to enable Claude Code
3. You may need to grant Terminal access permissions

> If you don't see the Claude Code option, make sure your Desktop App is up to date. Go to **claude.ai/download** and reinstall the latest version.

#### Step 3: Verify it's working

Once Claude Code is enabled, try asking Claude something simple like:

```
What files are in my current folder?
```

If Claude responds with a list of files from your computer, Claude Code is working!

### Why Do We Need This?

| Feature | Claude Desktop App alone | With Claude Code enabled |
|---------|------------------------|-------------------------|
| Chat with Claude | Yes | Yes |
| Connect external tools (Slack, Jira, etc.) | No | Yes |
| Access Connectors in Settings | No | Yes |
| Run terminal commands | No | Yes |
| Build skills & automations | Limited | Yes |

## EXECUTE

1. **Open Claude Desktop App**
2. **Enable Claude Code** — look for the Claude Code toggle in the **top-center** of the window
3. **Test it** — ask Claude "What files are in my current folder?" to verify Claude Code is active

If Claude responds by listing files, you're ready to connect tools!

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Where do you enable Claude Code in the Desktop App?",
    "header": "Install Quiz",
    "options": [
      {"label": "In the top-center of the Desktop App window", "description": ""},
      {"label": "By downloading a separate application", "description": ""},
      {"label": "Through your web browser at claude.ai", "description": ""},
      {"label": "In your computer's System Settings", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "In the top-center of the Desktop App window"

If correct: "That's right! Claude Code lives inside the Claude Desktop App — you enable it from the top-center toggle. Once enabled, you get access to Connectors, skills, and all the powerful features we'll use today."
If incorrect: "Claude Code is enabled inside the **Claude Desktop App** itself — look for the toggle in the **top-center** of the window. It's not a separate download. Once enabled, you can connect external tools through Settings → Connectors."
