# Block 2: Chaining Skills into Workflows

## EXPLAIN

**Chaining** means connecting skills so the output of one becomes the input of the next. Like an assembly line.

### The Concept

```
/collect-data  →  produces data.md
/analyze-data  →  reads data.md  →  produces analysis.md
/make-report   →  reads analysis.md  →  produces report.md
```

Each skill does ONE thing well. Together, they form a complete workflow.

### Why Chain Instead of One Big Skill?

| One big skill | Chained skills |
|--------------|----------------|
| Does everything at once | Each does one thing |
| Hard to debug (which step failed?) | Easy to debug (which skill failed?) |
| Can't reuse parts | Reuse skills in different workflows |
| Hard to modify | Change one skill without breaking others |
| All or nothing | Run partial workflow if needed |

### How to Chain Skills

**Method 1: Manual chaining (you run each one)**
```
You: /collect-feedback
(Claude collects feedback, saves to feedback.md)

You: /analyze-feedback
(Claude reads feedback.md, analyzes, saves to analysis.md)

You: /draft-response
(Claude reads analysis.md, drafts responses)
```

**Method 2: Workflow skill (one skill runs the chain)**
Create a "conductor" skill that calls the others:

```markdown
---
name: feedback-pipeline
description: "Run the full feedback workflow: collect → analyze → respond."
---

# Feedback Pipeline

## Steps
1. Execute the same steps as /collect-feedback:
   - Fetch messages from #customer-feedback (last 7 days)
   - Save to feedback-raw.md

2. Execute the same steps as /analyze-feedback:
   - Read feedback-raw.md
   - Categorize by topic
   - Rate sentiment
   - Save to feedback-analysis.md

3. Execute the same steps as /draft-response:
   - Read feedback-analysis.md
   - Draft response for each category
   - Save to feedback-responses.md

4. Output summary: "Pipeline complete. Files created: ..."
```

### Workflow Design Pattern

Think of your work as a pipeline:

```
COLLECT          PROCESS           DELIVER
(gather data) → (transform it) → (put it somewhere useful)
```

Examples:

| Role | Collect | Process | Deliver |
|------|---------|---------|---------|
| HR | Scan applications | Rank candidates | Create shortlist doc |
| Marketing | Monitor social mentions | Analyze sentiment | Draft report |
| Sales | Research prospect | Create talking points | Compile meeting brief |
| CS | Pull support tickets | Categorize issues | Generate weekly trends |
| Finance | Gather expense data | Categorize & total | Create expense report |

## EXECUTE

Build a second skill that chains with your Day 3 skill:

1. What does your Day 3 skill produce? (its output)
2. What would be useful to do NEXT with that output?
3. Create a second skill that takes that output and does the next step

Example:
```
Day 3 skill: /collect-feedback → produces feedback.md
Day 4 skill: /summarize-feedback → reads feedback.md → produces summary.md
```

Create the second skill:
```
mkdir -p .claude/skills/your-second-skill
```

Then write the SKILL.md. Make sure it references the output file from your first skill.

Test the chain:
1. Run `/first-skill`
2. Run `/second-skill`
3. Check: does the second skill correctly use the first skill's output?

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Why is it better to chain 3 small skills than have 1 big skill?",
    "header": "Chaining Quiz",
    "options": [
      {"label": "It runs faster", "description": ""},
      {"label": "It looks more impressive", "description": ""},
      {"label": "Each skill is easier to debug, reuse, and modify independently", "description": ""},
      {"label": "Claude prefers smaller skills", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Each skill is easier to debug, reuse, and modify independently"

If correct: "Exactly! Small, focused skills are like LEGO bricks — you can rearrange them into different workflows. If one breaks, you fix just that one. If you need a new workflow, you might already have skills that fit."
If incorrect: "The main benefit is modularity. Small skills are: (1) easier to debug — you know which step failed, (2) reusable — use the same skill in different workflows, (3) easier to modify — change one without breaking others. Think of them as LEGO bricks for your work."
