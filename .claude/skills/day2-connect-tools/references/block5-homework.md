# Block 5: Homework — Connect More Tools

## EXPLAIN

You now know how to connect tools via MCP, run cross-tool queries, and troubleshoot issues. Time to expand your setup.

### Your Homework

**Before tomorrow (Day 3), complete these:**

1. **Connect at least 2 more MCP servers** for tools you use at work
2. **Run 1 cross-tool query** that does something genuinely useful
3. **Write down 3 ideas** for tasks you'd like to automate (you'll build one on Day 3)

### Why This Matters for Day 3

Tomorrow you'll build your first **Skill** — a reusable custom command. The more tools you have connected, the more powerful your skill can be.

For example:
- With just file access → you can make a skill that generates reports from local data
- With Slack + files → you can make a skill that pulls Slack data and creates reports
- With Slack + Google Sheets + Calendar → you can make a skill that automates your entire weekly routine

### Automation Ideas Starter List

Think about tasks where you currently:
- **Copy-paste between tools** → Claude can read from one and write to another
- **Follow the same steps every time** → Claude can follow those steps as a skill
- **Compile information from multiple sources** → Claude can gather and summarize
- **Format data repeatedly** → Claude can transform data into any format

| Pattern | Example |
|---------|---------|
| Collect → Summarize | Slack messages → weekly digest |
| Monitor → Alert | New entries in spreadsheet → Slack notification |
| Request → Generate | "New hire starting Monday" → full onboarding pack |
| Analyze → Report | Raw data → formatted report with insights |

## EXECUTE

1. Install 2 more MCP servers from the catalog (Block 2)
2. Test each one works with a simple query
3. Try a cross-tool query that helps your actual work
4. Write your 3 automation ideas in a file:

```bash
# In your claude-camp folder, ask Claude:
"Create a file called automation-ideas.md with 3 task automation ideas
based on the tools I have connected. For each idea, list:
- The task I do manually today
- Which tools are involved
- What the automated version would look like
- How much time it would save per week"
```

This file will be your starting point for Day 3.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What's the most important thing to bring to Day 3?",
    "header": "Homework Check",
    "options": [
      {"label": "A list of all MCP servers that exist", "description": ""},
      {"label": "2+ connected tools and 3 automation ideas from your real work", "description": ""},
      {"label": "A finished automation project", "description": ""},
      {"label": "Nothing — Day 3 starts fresh", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "2+ connected tools and 3 automation ideas from your real work"

If correct: "Perfect! Day 3 is all about building YOUR skill for YOUR work. The connected tools give Claude the reach, and your ideas give it direction. See you tomorrow!"
If incorrect: "Tomorrow you'll build a real automation for your job. To make the most of it, have your tools connected (so Claude can access them) and your ideas ready (so you know what to build). It's the preparation that makes Day 3 productive."
