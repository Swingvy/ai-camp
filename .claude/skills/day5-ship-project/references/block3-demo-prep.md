# Block 3: Prepare Your Demo

## EXPLAIN

You have 3 minutes to show the group what you built. Make it count.

### The Demo Structure

```
[0:00 - 0:30]  THE PROBLEM
"Every week, I spend 45 minutes doing X. Here's what that looks like..."

[0:30 - 2:00]  THE SOLUTION (live demo)
"Now watch what happens when I type /my-skill..."
(run the skill live, show the output)

[2:00 - 2:30]  THE IMPACT
"What used to take 45 minutes now takes 2 minutes."

[2:30 - 3:00]  WHAT'S NEXT
"Next, I plan to add Y and connect Z."
```

### Tips for a Great Demo

**DO:**
- Start with the pain ("Every Monday morning, I dread doing X...")
- Run the skill LIVE — the audience wants to see it work
- Show the actual output — zoom in on the result
- Share specific numbers ("45 min → 2 min")
- Be honest about limitations ("It doesn't handle X yet")

**DON'T:**
- Read your SKILL.md code
- Explain MCP or technical details
- Apologize ("It's not perfect but...")
- Rush through the output — let people see it

### Backup Plan

What if the live demo fails? (It happens!)
- Have a screenshot of a successful run
- Describe what WOULD happen: "Normally it pulls 50 messages from Slack and..."
- Show the output file from your last successful test

### Presentation Tip: The "So What" Test

For every sentence in your demo, ask: "So what? Why should the audience care?"

| Bad | Good (passes "so what" test) |
|-----|-----|
| "I used MCP to connect Slack" | "Now Claude can read our customer feedback channel directly" |
| "The skill has 5 steps" | "In 30 seconds, it does what takes me 45 minutes" |
| "The output is in markdown" | "The report is ready to paste into our weekly Slack update" |

## EXECUTE

Prepare your demo:

1. **Write your opening line** (the problem):
   "Every [time period], I spend [time] doing [task]..."

2. **Test your skill one more time** — make sure it runs cleanly

3. **Write your closing line** (the impact):
   "What used to take [X] now takes [Y]."

4. **Practice once**: time yourself — aim for under 3 minutes

5. **Prepare backup**: take a screenshot of your output

Save your demo notes:
```
Create a file called demo-notes.md with:
- My opening line (the problem)
- What I'll type to run the demo
- My closing line (the impact)
- What's next (future improvements)
```

## QUIZ

No quiz — just a confidence check:

```
AskUserQuestion({
  "questions": [{
    "question": "Are you ready to demo?",
    "header": "Demo Readiness",
    "options": [
      {"label": "Yes, let's go!", "description": "Your skill works and you know what to say."},
      {"label": "Almost — need a few more minutes", "description": "Polish your demo notes and test once more."},
      {"label": "My skill isn't working yet", "description": "Let's debug it together right now."}
    ],
    "multiSelect": false
  }]
})
```

If "not working": immediately help debug — read the SKILL.md, check MCP connections, test step by step. The goal is to get SOMETHING working for the demo, even if simplified.
