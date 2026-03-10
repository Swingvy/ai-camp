# Block 2: Write & Validate Your PRD

## EXPLAIN

A **PRD (Product Requirements Document)** is a one-page summary of your project: what problem it solves, how it works, and how to use it.

### Why Write a PRD?

1. **For yourself**: Forces you to articulate what you built and why
2. **For your team**: Others can understand and use your skills
3. **For future you**: When you come back in 3 months, you'll know what this does

### PRD Template

```markdown
# [Project Title]

## Problem
> One line: whose problem, what problem, how you solve it

- **Current state**: (specific numbers — how many, how long, how often)
- **Desired state**: (what it looks like when working)
- **Success criteria**: (1-2 measurable outcomes)

## Skills

| # | Skill name | Description | Status |
|---|-----------|-------------|--------|
| 1 | `/my-skill-1` | input → output | Working / In progress |
| 2 | `/my-skill-2` | input → output | Working / In progress |

## MCP Connections Used
- Tool 1: what data it provides
- Tool 2: what data it provides

## How to Use
1. Step 1
2. Step 2
3. Step 3

## Impact
- Before: (time/effort required manually)
- After: (time/effort with this solution)
```

### PRD Validation

Your PRD must pass these checks:

| # | Item | Required? |
|---|------|-----------|
| 1 | Project title (`#` heading) | Yes |
| 2 | Problem section (`## Problem`) | Yes |
| 3 | Current state (10+ characters) | Yes |
| 4 | Desired state (10+ characters) | Yes |
| 5 | Success criteria (10+ characters) | Yes |
| 6 | Skills section with 1+ skill listed | Yes |
| 7 | MCP Connections section | Yes |
| 8 | How to Use section | Yes |
| 9 | Impact section | Yes |

## EXECUTE

1. Write your PRD. You can ask Claude:
```
Based on the project I just built in .claude/skills/,
write a PRD using this template: [paste template above]
Fill in real details about my project.
```

2. Review what Claude wrote — make sure the numbers and descriptions are accurate

3. Ask Claude to validate:
```
Read my PRD and check it against the validation checklist.
Does it pass all 9 items?
```

4. Fix any issues until you get a PASS on all items

5. Save as `PRD.md` in your project root

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What goes in the 'Impact' section of your PRD?",
    "header": "PRD Quiz",
    "options": [
      {"label": "The code that runs your skill", "description": ""},
      {"label": "A list of all MCP servers available", "description": ""},
      {"label": "Before (manual effort) vs. After (with your solution) — the measurable difference", "description": ""},
      {"label": "Your personal opinion about AI", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Before vs. After — the measurable difference"

If correct: "Right! Impact is the 'so what?' of your project. 'Before: 45 minutes every week compiling reports manually. After: 2 minutes with /weekly-report.' That concrete comparison shows the value."
If incorrect: "The Impact section shows the before/after comparison. Example: 'Before: 45 min/week compiling reports manually. After: 2 min/week with /weekly-report.' This concrete difference is what makes your project compelling — it shows real value."
