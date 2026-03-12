# Block 4: Enhance Your Skill

## EXPLAIN

Now apply today's techniques to upgrade your existing skills. Pick one or more enhancements.

### Enhancement Menu

| Enhancement | Difficulty | Impact |
|-------------|-----------|--------|
| Chain with a second skill | Medium | More complete workflow |
| Add input validation | Easy | Fewer errors |
| Improve output formatting | Easy | More professional results |
| Add error messages | Easy | Better user experience |
| Add conditional logic | Medium | Smarter behavior |

### Enhancement Examples

**Before (Basic Day 3 skill):**
```markdown
## Steps
1. Fetch messages from #team-updates (last 7 days)
2. Group by project
3. Summarize each project
4. Save as weekly-report.md
```

**After (Enhanced Day 4 skill):**
```markdown
## Steps
1. Validate inputs:
   - Check that Slack MCP is connected
   - If not: tell user "Please connect Slack first: /install slack"

2. Fetch data:
   - Fetch messages from #team-updates (last 7 days)
   - Fetch messages from #blockers (last 7 days)

3. Validate data:
   - If no messages found in any channel: notify the user and stop
   - If less than 3 messages: warn "Low activity this week"

4. Process:
   - Group Slack messages by project
   - Identify blockers from #blockers channel
   - Calculate activity stats (messages per project, top contributors)

5. Format output using EXACTLY this template:
   [detailed template]

6. Save as reports/weekly-{YYYY-MM-DD}.md

7. Output confirmation:
   "Report saved. Summary: {n} projects, {n} updates, {n} blockers"

## Error handling
- Slack MCP not connected: "Please connect Slack first: /install slack"
- No messages found: "No team updates found for this period. Is #team-updates the right channel?"
- Channel not accessible: "Cannot access #{channel}. Check bot permissions."
```

### The Enhancement Process

```
1. Read your current SKILL.md
2. Pick 1-2 enhancements from the menu
3. Edit SKILL.md to add them
4. Test the enhanced version
5. Compare: is it noticeably better?
```

## EXECUTE

Time to enhance your skill. Here's the process:

1. Read your current SKILL.md
2. Choose at least 1 enhancement from the menu above
3. Apply the enhancement — edit your SKILL.md
4. Test the enhanced version
5. Compare the output with the previous version

If you need help deciding which enhancement, think about:
- What annoyed you when testing yesterday? → fix that
- Is the output format good enough? → improve formatting
- What do you do manually after the skill runs? → chain a second skill

Ask Claude for help:
```
Read my skill at .claude/skills/[name]/SKILL.md.
I want to enhance it by [chaining / adding error handling / improving output format].
Suggest the specific changes I should make.
```

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "You've enhanced your skill. How do you know if the enhancement actually improved things?",
    "header": "Enhancement Quiz",
    "options": [
      {"label": "The SKILL.md file is longer", "description": ""},
      {"label": "Run it and compare the output with the previous version — is it faster, more complete, or more reliable?", "description": ""},
      {"label": "If it doesn't crash, it's improved", "description": ""},
      {"label": "Ask Claude if it's better", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Run it and compare the output with the previous version"

If correct: "Right! The proof is in the output. A longer SKILL.md doesn't mean better. Run both versions and compare: is the output faster? More complete? Does it handle edge cases? That's how you know."
If incorrect: "The only way to judge an enhancement is to compare results. Run the old version and the new version. Is the output better? Faster? More reliable? More complete? If yes, the enhancement worked. If not, simplify."
