# Block 4: CLAUDE.md — Teach Claude About You

## EXPLAIN

CLAUDE.md is a special file that Claude reads at the start of every conversation. It's like a briefing document — it tells Claude who you are, what you do, and how you like things done.

**Without CLAUDE.md:** Claude is a smart stranger. It can help, but it doesn't know your context.

**With CLAUDE.md:** Claude is a smart colleague. It knows your role, your tools, your preferences, and your team.

### What to put in CLAUDE.md

```markdown
# About Me
- Role: [Your job title and team]
- Company: [Company name, what we do]

# My Daily Tools
- Slack: channels I monitor (#sales, #product-feedback)
- Google Docs: meeting notes, proposals
- Jira: project tracking, sprint boards
- HubSpot: customer data, sales pipeline

# My Common Tasks
- Monday: compile weekly sales numbers from Google Docs
- Wednesday: write team status update for Slack
- Friday: review customer feedback and categorize issues

# Preferences
- Format: bullet points over paragraphs
- Tone: professional but friendly
- Always use tables for comparisons
- Date format: YYYY-MM-DD
```

### Where does CLAUDE.md go?

In the root of your project folder:
```
claude-camp/
├── CLAUDE.md        ← here
├── my-tasks.md
└── my-tasks-compact.md
```

### The power of CLAUDE.md

| Without | With |
|---------|------|
| "Summarize this data" → generic summary | "Summarize this data" → summary formatted as you like, focused on metrics you care about |
| "Draft an email" → generic tone | "Draft an email" → matches your writing style |
| "What should I work on?" → no idea | "What should I work on?" → knows your Monday routine |

## EXECUTE

Let's create your CLAUDE.md using a quick survey. Claude will ask you structured questions, then auto-generate the file.

Instead of writing everything from scratch, answer the following survey questions. Claude will use your answers to generate a personalized CLAUDE.md.

**Step 1: Answer the survey**

```
AskUserQuestion({
  "questions": [
    {
      "question": "What is your role?",
      "header": "Your Role",
      "options": [
        {"label": "HR / People Ops", "description": "Hiring, onboarding, people management"},
        {"label": "Finance / Accounting", "description": "Budgets, expenses, financial reporting"},
        {"label": "Marketing", "description": "Content, campaigns, social media, brand"},
        {"label": "Sales / Business Development", "description": "Pipeline, deals, client relationships"}
      ],
      "multiSelect": false
    },
    {
      "question": "Which tools do you use daily? (Select all that apply)",
      "header": "Daily Tools",
      "options": [
        {"label": "Slack", "description": "Team messaging and channels"},
        {"label": "Google Workspace (Gmail, Docs, Calendar, Meet)", "description": "Email, documents, scheduling, video calls"},
        {"label": "Atlassian (Jira, Confluence)", "description": "Project tracking and wiki"},
        {"label": "HubSpot", "description": "CRM, marketing, sales tools"}
      ],
      "multiSelect": true
    },
    {
      "question": "Which additional tools do you use?",
      "header": "More Tools",
      "options": [
        {"label": "Dropbox", "description": "File storage and sharing"},
        {"label": "Google Meet", "description": "Video conferencing"},
        {"label": "Google Calendar", "description": "Scheduling and events"},
        {"label": "None of these", "description": "Only the tools selected above"}
      ],
      "multiSelect": true
    }
  ]
})
```

**Step 2: Tell Claude your common tasks**

After the survey, briefly tell Claude:
- Your 2-3 most common weekly tasks
- Any formatting preferences (bullet points, tables, etc.)

**Step 3: Generate CLAUDE.md**

Ask Claude:
```
Based on my survey answers and the tasks I described,
create a CLAUDE.md file in this folder.
```

**Step 4: Test the difference**

```
Without context: "Write a weekly summary"
(Exit Claude, restart, now CLAUDE.md is loaded)
With context: "Write a weekly summary"
```

Compare the two outputs. The second one should be noticeably more relevant to your work.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What is CLAUDE.md?",
    "header": "CLAUDE.md Quiz",
    "options": [
      {"label": "A configuration file for installing Claude", "description": ""},
      {"label": "A briefing document that tells Claude about you, your role, tools, and preferences", "description": ""},
      {"label": "A log file that records your conversations", "description": ""},
      {"label": "A programming file that customizes Claude's behavior", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "A briefing document that tells Claude about you, your role, tools, and preferences"

If correct: "Right! Think of it as your profile page for Claude. The better your CLAUDE.md, the more useful Claude becomes — because it understands YOUR context."
If incorrect: "CLAUDE.md is your personal briefing document. It tells Claude who you are, what tools you use, what tasks you do, and how you like things formatted. Claude reads it at the start of every conversation, so it always knows your context."
