# Block 0: What is a Skill?

## EXPLAIN

A **Skill** is a reusable set of instructions that Claude follows when you invoke it. Think of it as a custom command — you type `/skill-name` and Claude does something specific, the same way, every time.

### Not Code — Instructions

A skill is NOT a program. It's a document (SKILL.md) written in plain language that tells Claude:
- What to do
- In what order
- What format to use
- How to handle problems

You already know how to write good instructions for Claude (Day 1). A skill is just those instructions saved in a file so you can reuse them.

### Before vs After

**Without a skill (every time you need a weekly report):**
```
You: "Can you check Slack #team-updates for this week,
      pull the key updates, group them by project,
      format as bullet points with owner names,
      and save as a markdown file?"
```
You type this (or something like it) every single week.

**With a skill:**
```
You: /weekly-report
```
Claude does all of the above automatically. Same quality, every time, in seconds.

### Where Skills Live

```
your-project/
├── CLAUDE.md
├── .claude/
│   └── skills/
│       └── weekly-report/
│           └── SKILL.md     ← your skill instructions
```

### Live Demo

Let me show you a real skill in action. I'll create a simple one and run it:

```markdown
# File: .claude/skills/greet/SKILL.md
---
name: greet
description: "Greet the user with today's date and a motivational quote."
---

# Daily Greeting

When invoked:
1. Get today's date
2. Say good morning with the date
3. Add a short motivational quote
4. List 3 suggested focus areas based on the day of the week
```

After creating this file, typing `/greet` makes Claude do exactly this, every time.

### Discover Existing Skills

Before building your own, explore what others have already created. Visit **https://skills.sh/** — a directory of community-built skills you can browse and install.

This is like an app store for Claude Code skills. You might find:
- Skills similar to what you want to build (use as inspiration)
- Ready-to-use skills that solve your exact problem
- Examples of well-structured SKILL.md files to learn from

## EXECUTE

**Step 1: Explore existing skills**

Visit https://skills.sh/ in your browser. Browse through the available skills and find 2-3 that look interesting or relevant to your work.

**Step 2: Create a simple demo skill**

In your `claude-camp` folder, ask Claude:

```
Create a skill called "daily-checklist" that:
- Greets me with today's date
- Shows a checklist of 5 items I need to do today
- The checklist should be based on the day of the week
  (Monday = planning tasks, Friday = wrap-up tasks, etc.)

Create it as .claude/skills/daily-checklist/SKILL.md
```

After Claude creates it, test it:
```
/daily-checklist
```

See how the skill works. Does it do what you expected?

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What is a Claude Code Skill?",
    "header": "Skill Concept Quiz",
    "options": [
      {"label": "A programming language for Claude", "description": ""},
      {"label": "A reusable set of instructions saved as SKILL.md that Claude follows when you type /skill-name", "description": ""},
      {"label": "An extension you download from a store", "description": ""},
      {"label": "A certification you earn by completing training", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "A reusable set of instructions saved as SKILL.md that Claude follows when you type /skill-name"

If correct: "Exactly! A skill is just saved instructions. No coding, no downloads, no installations. You write what you want Claude to do in plain language, save it as SKILL.md, and invoke it anytime with /skill-name."
If incorrect: "A skill is simply a SKILL.md file with instructions written in plain language. You save it in `.claude/skills/your-skill-name/SKILL.md`, and then you can run it anytime by typing `/your-skill-name`. No coding required — it's just well-structured instructions."
