# Block 0: Plan Your Project

## EXPLAIN

Today you ship a real project. Not a practice exercise — something you'll use at work on Monday.

### What Makes a Good Final Project?

| Criteria | Why |
|----------|-----|
| Solves YOUR real problem | You'll actually use it |
| Uses 1+ MCP connections | Connects to real tools |
| Has 1+ custom skills | Reusable automation |
| Can demo in 2 minutes | Focused and complete |
| Works today | Done > perfect |

### Scoping: The Smallest Useful Thing

The #1 mistake is trying to do too much. Ask yourself:

```
"What is the SMALLEST version that would genuinely help me?"
```

| Too big | Just right |
|---------|-----------|
| "Automate our entire hiring pipeline" | "Generate interview prep sheets from job descriptions" |
| "Build a complete reporting system" | "Weekly report from Slack + Linear" |
| "Full customer feedback analysis platform" | "Categorize this week's support tickets" |

### Project Template

```
PROJECT NAME: _______________

PROBLEM (1 sentence):
"Every [time period], I spend [time] doing [task] because [reason]."

SOLUTION (1 sentence):
"A skill that [does what] using [which tools], saving [time]."

SKILLS I NEED:
1. /skill-name-1: does what
2. /skill-name-2: does what (optional)

MCP CONNECTIONS NEEDED:
- Tool 1: for what data
- Tool 2: for what action

SUCCESS = I can type /skill-name and get [specific output].
```

### Reuse What You've Built

You already have:
- Day 1: CLAUDE.md (your context)
- Day 2: MCP connections (your tools)
- Day 3: A working skill (your foundation)
- Day 4: Enhanced skill + second skill (your workflow)

Your final project can be an evolution of what you've already built!

## EXECUTE

Fill in the project template:

1. Define your problem in 1 sentence
2. Define your solution in 1 sentence
3. List the skills you need (1-3)
4. List the MCP connections you'll use
5. Define what "done" looks like

Share your plan with the instructor or a buddy for a quick sanity check:
- Is it scoped small enough for today?
- Do you have the MCP connections already?
- Is the output clearly defined?

If the plan is too big, ask: "What's the ONE skill version of this?"

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Your project plan is: 'Build a complete employee management system with onboarding, performance reviews, and payroll.' Is this a good Day 5 scope?",
    "header": "Scoping Quiz",
    "options": [
      {"label": "Yes, go big or go home", "description": ""},
      {"label": "No — pick ONE part (like onboarding checklist generator) and ship that", "description": ""},
      {"label": "Yes, if you work fast enough", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "No — pick ONE part"

If correct: "Right! A complete employee management system is a month-long project. An onboarding checklist generator is a 2-hour project. Ship the small thing that works. You can always expand later."
If incorrect: "Always pick the smallest useful slice. 'Complete employee management system' = months of work. 'Generate onboarding checklist from new hire info' = 2 hours and actually works today. Ship small, expand later."
