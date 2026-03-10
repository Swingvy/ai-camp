# Block 0: Welcome

## EXPLAIN

Welcome to the Claude Code Internal Training Camp.

**What is Claude Code?**
Claude Code is not a chatbot. It's an AI agent that lives in your terminal — it can read files, write files, search the web, connect to your tools, and execute tasks directly on your computer.

Think of it like having a super-capable assistant sitting right inside your computer, who can:
- Read and write documents for you
- Pull data from Slack, Notion, Google Drive
- Automate tasks you do every day
- Build custom tools tailored to YOUR specific job

**What you'll build this week:**

| Day | What you learn | What you build |
|-----|---------------|----------------|
| 1 (Today) | Install + first conversations | Your CLAUDE.md profile |
| 2 | Connect your tools (MCP) | Slack/Notion/Drive connections |
| 3 | Build a Skill | Your first custom command |
| 4 | Advanced workflows | Multi-skill automation |
| 5 | Ship your project | A real solution for your job |

**By Friday**, you'll have a working system that makes part of your job faster. Not a demo. Not a toy. Something you'll actually use on Monday.

**Ground rules:**
- There are no stupid questions — you're not expected to be technical
- If something doesn't work, that's normal — we'll fix it together
- The goal is YOUR workflow, not theoretical knowledge

## EXECUTE

Take a moment to think about your daily work:

1. Open a notes app (or paper)
2. Write down 3 tasks you do repeatedly (daily or weekly)
3. For each task, estimate how long it takes
4. Star the one that's most annoying or time-consuming

Example:
```
1. Compile weekly team status from Slack messages — 45 min/week ⭐
2. Format expense reports from receipts — 30 min/week
3. Draft meeting agendas from last meeting's notes — 20 min/meeting
```

Keep this list — you'll use it on Day 3 when you build your first skill.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What is Claude Code?",
    "header": "Quick Check",
    "options": [
      {"label": "A chatbot like ChatGPT", "description": ""},
      {"label": "An AI agent in your terminal that can read, write, and execute tasks", "description": ""},
      {"label": "A programming language", "description": ""},
      {"label": "A website builder", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "An AI agent in your terminal that can read, write, and execute tasks"

If correct: "Exactly! It's not just chat — it takes action directly on your computer."
If incorrect: "Not quite. Claude Code is an AI agent that lives in your terminal. Unlike chatbots, it can actually DO things — read files, write documents, connect to your tools, and automate tasks."
