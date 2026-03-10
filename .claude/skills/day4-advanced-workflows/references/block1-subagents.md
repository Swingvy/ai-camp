# Block 1: Subagents — Parallel Work

## EXPLAIN

A **subagent** is like hiring a temporary assistant to do part of the job while you continue with other work.

### Without Subagents (Sequential)
```
Step 1: Fetch Slack data         (30 seconds)
Step 2: Fetch Google Drive data  (30 seconds)
Step 3: Fetch Linear issues      (30 seconds)
Step 4: Combine and summarize    (10 seconds)
Total: ~100 seconds
```

### With Subagents (Parallel)
```
Step 1: Fetch Slack data        ─┐
Step 2: Fetch Google Drive data  ├─ all at once (30 seconds)
Step 3: Fetch Linear issues     ─┘
Step 4: Combine and summarize    (10 seconds)
Total: ~40 seconds
```

Same result, much faster.

### How to Add Subagents to Your Skill

In your SKILL.md, you can instruct Claude to use subagents:

```markdown
## Steps
1. Use the Agent tool to launch 3 parallel tasks:
   - Agent 1: Fetch all messages from #team-updates on Slack (last 7 days)
   - Agent 2: List recently modified files in the "Reports" Google Drive folder
   - Agent 3: Fetch open Linear issues assigned to the current user

2. Wait for all agents to complete

3. Combine the results:
   - Slack messages → "Team Updates" section
   - Drive files → "Recent Documents" section
   - Linear issues → "Open Tasks" section

4. Format into the output template and save
```

### When to Use Subagents

| Use subagents when... | Don't use when... |
|----------------------|-------------------|
| Fetching from multiple sources | Steps depend on each other |
| Each task is independent | Step 2 needs Step 1's result |
| Speed matters | There's only one data source |
| Tasks are read-only | Tasks modify shared data |

### Key Rule

Subagents are for **independent, parallel tasks**. If Step 2 needs the result of Step 1, they can't run in parallel.

```
Independent (can parallelize):     Dependent (must be sequential):
  Fetch Slack ──┐                    Fetch data ──→ Process data ──→ Save
  Fetch Drive ──┤                    (each step needs the previous result)
  Fetch Linear ─┘
```

## EXECUTE

Look at your Day 3 skill and identify:

1. Are there steps that fetch data from different sources?
2. Are any of those steps independent (don't need each other's results)?
3. If yes, add subagent instructions to your SKILL.md:

```markdown
## Steps (updated with subagents)
1. Launch parallel agents to gather data:
   - Agent A: [your first data source]
   - Agent B: [your second data source]
2. Combine results from both agents
3. [rest of your steps]
```

If your skill only has one data source, that's fine — not every skill needs subagents. Instead, try creating a NEW simple skill that gathers data from 2+ sources:

```
Create a skill called "morning-briefing" that:
- Fetches: today's calendar events
- Fetches: unread Slack messages from my key channels
- Fetches: my open tasks from [project tool]
- Combines into a single morning summary
Use subagents for the 3 fetch steps.
```

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Your skill has 3 steps: (1) Fetch Slack data, (2) Fetch Drive files, (3) Use Slack data to search Drive. Which steps can run in parallel?",
    "header": "Subagent Quiz",
    "options": [
      {"label": "All 3 can run in parallel", "description": ""},
      {"label": "Steps 1 and 2 can run in parallel, but Step 3 must wait", "description": ""},
      {"label": "None — they must all be sequential", "description": ""},
      {"label": "Steps 2 and 3 can run in parallel", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Steps 1 and 2 can run in parallel, but Step 3 must wait"

If correct: "Exactly! Steps 1 and 2 are independent — they don't need each other. But Step 3 needs Slack data (from Step 1) to know what to search for in Drive. So 1 and 2 run in parallel, then 3 runs after 1 completes."
If incorrect: "Step 3 says 'Use Slack data to search Drive' — it DEPENDS on Step 1's result. So Step 3 must wait for Step 1. But Steps 1 and 2 are independent (fetching from different tools), so they can run in parallel. The key: if a step needs another step's output, it must wait."
