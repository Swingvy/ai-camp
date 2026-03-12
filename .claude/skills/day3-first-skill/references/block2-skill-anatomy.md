# Block 2: Anatomy of SKILL.md

## EXPLAIN

Every skill has the same structure. Master this template and you can build any skill.

### The Structure

```markdown
---
name: skill-name
description: "What it does and when to use it. Trigger words here."
---

# Skill Title

## What this skill does
(2-3 sentences explaining the problem and solution)

## Inputs needed
- Input 1: where it comes from
- Input 2: where it comes from

## Steps
1. First action
2. Second action
3. Third action
4. ...

## Output format
(Exactly what the result looks like — show a template)

## Error handling
- If [problem]: do [solution]
- If no data found: say [message]
```

### Let's Break Down Each Part

**1. Frontmatter (the `---` section)**
```yaml
---
name: weekly-report        # lowercase, hyphens, no spaces
description: "Generate weekly status report from Slack. Use for 'weekly report', 'status update', 'weekly summary'."
---
```
- `name`: what you type after `/` to run it
- `description`: tells Claude WHEN to suggest this skill. Include trigger words and phrases people might use.

**2. Title & What it does**
```markdown
# Weekly Status Report

## What this skill does
Collects team updates from Slack #team-updates for the past 7 days,
groups them by project, and produces a formatted status report.
```
Clear. Specific. No ambiguity.

**3. Inputs needed**
```markdown
## Inputs needed
- Slack channel: #team-updates (via MCP)
- Time range: last 7 days
- No user input required (fully automatic)
```
Tell Claude where to get data. If it needs to ask the user something, say so.

**4. Steps**
```markdown
## Steps
1. Read all messages from #team-updates for the past 7 days
2. Group messages by project name (look for project tags or keywords)
3. For each project, extract: key updates, blockers, next steps
4. Count total messages and unique contributors
5. Format into the output template below
6. Save as `reports/weekly-{YYYY-MM-DD}.md`
```
Be specific. Each step should be one action. Number them.

**5. Output format**
```markdown
## Output format
# Weekly Status Report — {date range}

**Summary**: {total} updates from {n} team members across {n} projects

## {Project Name}
- **Updates**: (bullet points)
- **Blockers**: (bullet points or "None")
- **Next steps**: (bullet points)

(repeat for each project)
```
Show Claude EXACTLY what the output should look like.

**6. Error handling**
```markdown
## Error handling
- If Slack MCP is not connected: tell the user to run `claude mcp add slack`
- If no messages found in the date range: output "No updates found for this period"
- If a message can't be categorized: put it under "Uncategorized"
```
What should Claude do when things go wrong?

### Official Skill Creator

Anthropic provides an official **Skill Creator** skill that can help you build well-structured skills. You can find it at:
https://github.com/anthropics/skills/blob/main/skills/skill-creator/SKILL.md

This is a skill that builds other skills — it understands the anatomy above and can help you structure your SKILL.md correctly.

### Common Mistakes

| Mistake | Fix |
|---------|-----|
| Steps too vague ("process the data") | Be specific ("group by project, extract key updates") |
| No output format | Always show a template of the expected output |
| Forgetting error cases | Think: "What if there's no data? Wrong tool? Missing auth?" |
| Too ambitious | Start with 3-5 steps, expand later |

## EXECUTE

Read the full anatomy again and study this complete example:

```markdown
---
name: meeting-prep
description: "Prepare for a meeting by gathering context. Use for 'meeting prep', 'prepare for meeting', 'meeting brief'."
---

# Meeting Preparation Brief

## What this skill does
Gathers context for an upcoming meeting — previous notes, relevant
Slack discussions, and open action items — into a concise brief.

## Inputs needed
- Meeting topic: ask the user
- Slack channels: ask which channels are relevant
- Previous notes: check for files in `meetings/` folder

## Steps
1. Ask the user: "What meeting are you preparing for?"
2. Ask: "Which Slack channels have relevant discussions?"
3. Search those Slack channels for messages related to the meeting topic (last 14 days)
4. Check the `meetings/` folder for previous meeting notes on this topic
5. Compile a brief with: Background, Key Discussion Points, Open Questions, Previous Action Items
6. Save as `meetings/prep-{topic}-{date}.md`

## Output format
# Meeting Prep: {topic}
**Date**: {date}
**Prepared by**: Claude

## Background
(2-3 sentence summary of the topic based on Slack and previous notes)

## Key Discussion Points
1. (from Slack messages and previous notes)
2. ...

## Open Questions
- (unresolved items from previous meetings)

## Previous Action Items
- [ ] (item — owner — status)

## Error handling
- If no Slack channels specified: use #general as default
- If no previous meeting notes found: skip that section and note "No previous notes found"
- If Slack MCP not connected: create brief from local files only and note the limitation
```

Now, think about YOUR skill from Block 1. How would you map your task onto this anatomy?

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Which section of SKILL.md tells Claude EXACTLY what the result should look like?",
    "header": "Anatomy Quiz",
    "options": [
      {"label": "Frontmatter (name and description)", "description": ""},
      {"label": "Steps", "description": ""},
      {"label": "Output format", "description": ""},
      {"label": "Error handling", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Output format"

If correct: "Right! The output format section is crucial — it shows Claude a template of exactly what the result should look like. Without it, Claude guesses, and the output quality varies every time."
If incorrect: "The Output format section shows Claude a template of the exact result structure. Steps tell Claude WHAT to do, but Output format tells Claude what the RESULT should look like. This ensures consistent, high-quality output every time you run the skill."
