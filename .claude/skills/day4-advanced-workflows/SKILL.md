---
name: day4-advanced-workflows
description: "Internal Camp Day 4: Advanced skills with subagents, multi-skill workflows, hooks, and team sharing. Use for \"Day 4\", \"advanced\", \"workflow\", \"subagent\", \"hooks\", \"team skills\"."
---

# Day 4: Advanced Skills & Workflows

This skill teaches participants to level up with subagents (parallel work), multi-skill workflows (chaining), hooks (automation), and sharing skills across the team.

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
| 0 | `references/block0-review-day3.md` | Review: show off your Day 3 skill |
| 1 | `references/block1-subagents.md` | Subagents — parallel work |
| 2 | `references/block2-chaining.md` | Chaining skills into workflows |
| 3 | `references/block3-hooks.md` | Hooks — automatic triggers |
| 4 | `references/block4-enhance-skill.md` | Enhance your skill with these techniques |
| 5 | `references/block5-team-repo.md` | Team skills repository + sharing |

---

## Key Concepts to Teach

### Subagents
```
Your skill says:
  "Use the Agent tool to fetch Slack data in the background
   while simultaneously fetching Linear data"

Result: Two things happen at once → combined into one output
```

### Chaining
```
/collect-feedback → produces feedback.md
/analyze-feedback → reads feedback.md → produces analysis.md
/draft-response  → reads analysis.md → produces response.md

One command triggers the full pipeline.
```

### Hooks
```json
// .claude/settings.json
{
  "hooks": {
    "after_tool_call": [{
      "tool": "Write",
      "command": "echo 'File created: check output'"
    }]
  }
}
```

### Workflow Combinations by Role

| Role | Skill 1 | Skill 2 | Workflow |
|------|---------|---------|----------|
| HR | `/scan-applications` | `/rank-candidates` | Screen → Rank |
| Marketing | `/collect-mentions` | `/draft-report` | Monitor → Report |
| Sales | `/prep-meeting` | `/send-summary` | Research → Brief |
| CS | `/categorize-tickets` | `/auto-response` | Classify → Draft reply |
| PM | `/gather-updates` | `/status-report` | Collect → Summarize |
| Finance | `/pull-transactions` | `/flag-anomalies` | Fetch → Analyze |

---

## Interaction Rules

- Start by having participants show their Day 3 skill (Block 0)
- For subagents: explain as "hiring an assistant to do part of the work"
- For chaining: explain as "assembly line — each station does one thing well"
- For hooks: explain as "automatic reactions — like a doorbell ringing when someone arrives"
- Focus on practical enhancement of their existing skill, not abstract concepts
- Git workflow for team repo: guide step by step (clone, branch, add, commit, push, PR)

---

## Start

```
AskUserQuestion({
  "questions": [{
    "question": "Where would you like to start?",
    "header": "Day 4: Advanced Skills & Workflows",
    "options": [
      {"label": "Block 0: Review Day 3", "description": "Show your skill + get feedback"},
      {"label": "Block 1: Subagents", "description": "Do multiple things in parallel"},
      {"label": "Block 2: Chaining Skills", "description": "Connect skills into a workflow"},
      {"label": "Block 3: Hooks", "description": "Automatic triggers and reactions"},
      {"label": "Block 4: Enhance Your Skill", "description": "Upgrade your existing skill"},
      {"label": "Block 5: Team Repository", "description": "Share skills across the team"}
    ],
    "multiSelect": false
  }]
})
```
