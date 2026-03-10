# Block 5: Share Your Skill

## EXPLAIN

You've built and tested a working skill. Now let's share it with the group.

### Why Share?

1. **Feedback** — others spot issues you missed
2. **Inspiration** — your skill gives others ideas for their own
3. **Team value** — your skill might help colleagues in the same role
4. **Practice** — explaining your skill reinforces your understanding

### Demo Format (2 minutes per person)

```
[0:00 - 0:20]  What's the task? (the manual version)
[0:20 - 0:40]  What does your skill do? (the automated version)
[0:40 - 1:30]  Live demo: run /your-skill-name
[1:30 - 2:00]  What would you improve next?
```

### Tips for a Good Demo

| Do | Don't |
|----|-------|
| Show the problem first, then the solution | Jump straight to the technical details |
| Run it live — real output | Show screenshots |
| Mention time saved | Talk about the code/syntax |
| Be honest about limitations | Pretend it's perfect |

### Receiving Feedback

After each demo, the group can suggest:
- "What if it also did X?"
- "Could it work for [similar task]?"
- "What happens if Y goes wrong?"

Write down the feedback — these become your improvement ideas for Day 4.

## EXECUTE

Prepare your 2-minute demo:

1. Write a one-sentence description of the problem your skill solves
2. Make sure your skill runs cleanly right now (test once more)
3. Have a backup plan if the live demo fails (screenshot of a previous successful run)
4. Think of one thing you'd like to improve

When it's your turn, go for it! Remember: every working skill is impressive — you built something from scratch that automates real work.

After all demos, write down:
- 1 skill from someone else that inspired you
- 1 feedback item you received that you want to implement
- Save these in `day3-feedback.md`

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What's the most important thing to show in your skill demo?",
    "header": "Demo Quiz",
    "options": [
      {"label": "The code inside SKILL.md", "description": ""},
      {"label": "The problem it solves (before) and the result it produces (after)", "description": ""},
      {"label": "How long it took to build", "description": ""},
      {"label": "All the error handling you added", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "The problem it solves (before) and the result it produces (after)"

If correct: "Exactly! Nobody cares about the internals — they care about the transformation. 'I used to spend 45 minutes on this, now it takes 30 seconds.' That's the story. Show the pain, then show the magic."
If incorrect: "The audience cares about impact, not implementation. Show them: 'This is what I used to do manually (painful), and this is what happens now when I type /my-skill (magic).' The before/after contrast is what makes people want to build their own skills."
