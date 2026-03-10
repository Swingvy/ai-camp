# Block 4: Test, Break, Fix, Improve

## EXPLAIN

Your skill is written. Now let's make it actually work well.

### The Test Cycle

```
Run skill → Check output → Find problems → Fix SKILL.md → Run again
     ↑                                                        │
     └────────────────────────────────────────────────────────┘
```

Expect to go through this cycle 3-5 times. That's normal. Professional developers do this too.

### What to Check

| Check | Question to ask |
|-------|----------------|
| Does it run? | Did Claude follow the steps without errors? |
| Is the output right? | Does it match the output format you specified? |
| Is the data correct? | Did it pull from the right sources? |
| Is it useful? | Would you actually use this result in your work? |
| Is it consistent? | Run it twice — do you get similar quality? |

### Common Problems & Fixes

**Problem: Claude skips steps**
```
Fix: Make steps more explicit. Instead of:
  "3. Summarize the data"
Change to:
  "3. Create a summary with: total count, top 3 items, key trend"
```

**Problem: Output format is different each time**
```
Fix: Add a literal template in the Output format section:
  "Use EXACTLY this format:"
  (then show the template)
```

**Problem: Claude asks too many questions**
```
Fix: Pre-answer the questions in the skill:
  "Default channel: #team-updates"
  "Default time range: last 7 days"
  "Do NOT ask the user unless the information is truly missing"
```

**Problem: Claude does too much**
```
Fix: Add boundaries:
  "Do NOT send any messages"
  "Do NOT modify existing files"
  "ONLY create new files in the reports/ folder"
```

**Problem: It breaks when there's no data**
```
Fix: Add error handling:
  "If no messages found: output 'No updates this period' and stop"
```

### Power Move: Ask Claude to Improve Your Skill

```
Read my skill at .claude/skills/my-skill/SKILL.md.
I ran it and the output was [describe what happened].
The problem is [describe the issue].
Suggest improvements to the SKILL.md.
```

Claude can help you debug and improve your own skill!

## EXECUTE

1. Run your skill: `/your-skill-name`
2. Check the output against the checklist above
3. Find at least 1 thing to improve
4. Edit SKILL.md (either manually or ask Claude to update it)
5. Run again — is it better?
6. Repeat until you're satisfied

Aim for at least 3 test cycles. Each one should make the skill noticeably better.

**Bonus challenge:** Try to break your skill on purpose:
- What happens if the Slack channel is empty?
- What happens if you run it twice in a row?
- What happens if the MCP server is disconnected?

Fix each issue you find.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Your skill gives different output formats each time you run it. What's the most likely fix?",
    "header": "Testing Quiz",
    "options": [
      {"label": "Delete the skill and start over", "description": ""},
      {"label": "Add 'Use EXACTLY this format:' with a literal template in the Output format section", "description": ""},
      {"label": "Run it more times until it stabilizes", "description": ""},
      {"label": "Change the skill name", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Add 'Use EXACTLY this format:' with a literal template"

If correct: "Right! When output varies, it means your format instructions aren't strict enough. Show Claude EXACTLY what the output should look like, word for word, and it will follow the template consistently."
If incorrect: "Inconsistent output means your format instructions are too loose. The fix is to add a literal template in the Output format section with 'Use EXACTLY this format:' followed by the exact structure you want. Claude is great at following specific templates."
