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
- Google Sheets: weekly sales tracker, expense reports
- Notion: team wiki, project boards

# My Common Tasks
- Monday: compile weekly sales numbers from Google Sheets
- Wednesday: write team status update for Slack
- Friday: review customer feedback and categorize issues

# Preferences
- Language: Korean (or English)
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

1. Launch Claude Code in your `claude-camp` folder
2. Ask Claude to help you create your CLAUDE.md:

```
Help me create a CLAUDE.md file. Ask me questions about:
- My role and team
- The tools I use daily
- My most common tasks
- My preferences for formatting and language

Then create the CLAUDE.md file based on my answers.
```

3. After Claude creates it, test the difference:

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
