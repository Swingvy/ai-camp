# Block 3: Write Your Skill

## EXPLAIN

Time to write your actual skill. You have everything you need:
- Your task from Block 1 (INPUT → PROCESS → OUTPUT)
- The anatomy from Block 2 (frontmatter, steps, output format, error handling)
- Your MCP connections from Day 2

### Writing Tips

**Start small.** Your first version doesn't need to do everything. Start with the core 3-5 steps. You can add more later.

**Use your own words.** SKILL.md is plain language. Write it the way you'd explain the task to a smart new colleague.

**Be specific about sources.** Don't say "get the data" — say "read messages from #product-feedback on Slack for the last 7 days."

**Define the output clearly.** Show a template. If the output is a table, draw the table. If it's a report, show the section headers.

### The Process

```
1. Create the folder:    mkdir -p .claude/skills/your-skill-name
2. Create the file:      Ask Claude to create SKILL.md based on your task description
3. Review and edit:      Read what Claude wrote, adjust to match your needs exactly
4. Test it:              /your-skill-name
5. Fix and improve:      Iterate based on what worked and what didn't
```

### Ask Claude for Help

You can ask Claude to help you write your skill! Try:

```
Help me create a skill called [name].

Here's what it should do:
- INPUT: [what data it starts with]
- STEPS: [what it does, step by step]
- OUTPUT: [what the result looks like]

The tools involved are: [Slack, Google Drive, etc.]

Create the SKILL.md file in .claude/skills/[name]/SKILL.md
```

Claude will draft the SKILL.md for you. Then review it and refine.

## EXECUTE

Now write your skill:

1. Tell me (or Claude in a fresh session) about the task you chose in Block 1:
   - What's the task name?
   - What are the inputs?
   - What are the steps?
   - What's the output?
   - What tools are involved?

2. Create the skill file. Either:
   - Ask Claude to generate it from your description, OR
   - Write it yourself using the anatomy template

3. Review the generated SKILL.md:
   - Are the steps specific enough?
   - Is the output format clear?
   - Are error cases covered?
   - Does the description include trigger words?

4. Save and prepare for testing (next block)

Remember: **done is better than perfect.** You can always improve it after testing.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "You're writing a skill and your Step 3 says 'process the data'. What should you do?",
    "header": "Writing Quiz",
    "options": [
      {"label": "Leave it — Claude will figure it out", "description": ""},
      {"label": "Make it specific: 'Group messages by sender, count messages per sender, sort by count descending'", "description": ""},
      {"label": "Remove Step 3 entirely", "description": ""},
      {"label": "Add more vague steps around it", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Make it specific"

If correct: "Exactly! Vague instructions get vague results. 'Process the data' could mean anything. 'Group messages by sender, count messages per sender, sort by count descending' tells Claude exactly what to do. Specificity is the key to reliable skills."
If incorrect: "Always replace vague instructions with specific ones. 'Process the data' is ambiguous — Claude might do something different each time. Instead, spell it out: 'Group by X, filter by Y, sort by Z.' The more specific your steps, the more consistent your results."
