# Block 0: Review Day 3

## EXPLAIN

Welcome to Day 4! Before we learn new techniques, let's see how your skills are working.

### Day 3 Recap

Yesterday you:
- Learned what a Skill is (reusable instructions in SKILL.md)
- Identified a repetitive task from your work
- Wrote your first SKILL.md
- Tested and iterated on it
- Demoed it to the group

### Today's Agenda

Today we level up with 3 power techniques:

| Technique | What it does | Analogy |
|-----------|-------------|---------|
| **Subagents** | Do multiple things in parallel | Hiring 2 assistants instead of 1 |
| **Chaining** | Connect skills into a pipeline | Assembly line — each station does one job |
| **Hooks** | Trigger actions automatically | Doorbell — rings automatically when someone arrives |

By the end of today, your simple skill will become a multi-step workflow.

## EXECUTE

1. Run your Day 3 skill one more time: `/your-skill-name`
2. While it runs, think about:
   - What takes the longest? (could subagents speed it up?)
   - What do you do AFTER the skill finishes? (could another skill handle that?)
   - What do you always check manually? (could a hook automate that check?)

3. Share with the group: "My skill does X, and the thing I wish it also did is Y."

## QUIZ

No quiz for this block. Just a readiness check:

```
AskUserQuestion({
  "questions": [{
    "question": "Is your Day 3 skill working?",
    "header": "Readiness Check",
    "options": [
      {"label": "Yes, it works well", "description": "Great! We'll enhance it today."},
      {"label": "It works but has some issues", "description": "We'll fix those as we enhance."},
      {"label": "No, it's broken", "description": "Let's fix it first before moving on."}
    ],
    "multiSelect": false
  }]
})
```

If broken: help fix the Day 3 skill before proceeding. Review SKILL.md, check MCP connections, test step by step.
