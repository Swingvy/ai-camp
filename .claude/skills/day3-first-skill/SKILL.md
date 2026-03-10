---
name: day3-first-skill
description: "Internal Camp Day 3: Build your first Claude Code Skill. Covers skill anatomy, writing SKILL.md, testing, and iteration. Use for \"Day 3\", \"first skill\", \"build skill\", \"make skill\", \"SKILL.md\"."
---

# Day 3: Build Your First Skill

This skill guides participants through creating their first reusable Claude Code Skill — from identifying a repetitive task to writing, testing, and refining a working SKILL.md.

---

## STOP PROTOCOL

> Same 2-turn protocol. Never violate.

```
Phase A: Explain + Execute instructions → STOP
Phase B: Quiz + feedback → next block
```

Phase A must end with:
```
---
👆 Try this yourself now.
When you're done, type "done" or "next" to continue.
```

---

## Block Map

| Block | File | Topic |
|-------|------|-------|
| 0 | `references/block0-what-is-skill.md` | What is a Skill? Live demo |
| 1 | `references/block1-find-your-task.md` | Identify your repetitive task |
| 2 | `references/block2-skill-anatomy.md` | Anatomy of SKILL.md |
| 3 | `references/block3-write-skill.md` | Write your skill |
| 4 | `references/block4-test-iterate.md` | Test, break, fix, improve |
| 5 | `references/block5-share.md` | Demo to the group |

---

## Role-specific Skill Ideas

When helping participants in Block 1, suggest relevant ideas based on their role:

| Role | Skill idea | What it does |
|------|-----------|--------------|
| HR | `/onboarding-checklist` | Generate personalized onboarding docs for new hires |
| Finance | `/expense-summary` | Summarize expense reports from shared drive |
| Marketing | `/social-draft` | Draft social media posts from product updates |
| Sales | `/deal-brief` | Compile customer info before a sales call |
| CS | `/ticket-summary` | Summarize support tickets by category |
| Ops | `/vendor-compare` | Compare vendor proposals side by side |
| PM | `/sprint-recap` | Generate sprint recap from project management tool |
| Legal | `/contract-review` | Extract key terms from contract drafts |

---

## Skill Template

When participants reach Block 3, provide this template:

```markdown
---
name: my-skill-name
description: "One line describing what this does and when to use it."
---

# Skill Title

## What this skill does
(2-3 sentences: what problem it solves, for whom)

## Inputs needed
- Input 1: (where it comes from)
- Input 2: (where it comes from)

## Steps
1. (First action)
2. (Second action)
3. (Third action)

## Output format
(Exactly what the result looks like)

## Error handling
- If [X] happens: do [Y]
- If no data found: say [Z]
```

---

## Interaction Rules

- Help participants think in terms of INPUTS → PROCESS → OUTPUT
- Encourage starting small (1 simple task) rather than building something complex
- Emphasize: "A skill is just instructions in plain language, not code"
- When testing skills, help debug by reading the SKILL.md and suggesting improvements
- Celebrate every working skill, no matter how simple

---

## Start

```
AskUserQuestion({
  "questions": [{
    "question": "Where would you like to start?",
    "header": "Day 3: Build Your First Skill",
    "options": [
      {"label": "Block 0: What is a Skill?", "description": "See a skill in action + understand the concept"},
      {"label": "Block 1: Find Your Task", "description": "Identify the repetitive task you'll automate"},
      {"label": "Block 2: Skill Anatomy", "description": "Learn the structure of SKILL.md"},
      {"label": "Block 3: Write Your Skill", "description": "Create your skill file"},
      {"label": "Block 4: Test & Iterate", "description": "Run it, break it, fix it, improve it"},
      {"label": "Block 5: Share", "description": "Demo your skill to the group"}
    ],
    "multiSelect": false
  }]
})
```
