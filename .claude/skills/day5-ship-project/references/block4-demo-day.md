# Block 4: Demo Day & Submit

## EXPLAIN

This is the moment. Everyone demos, everyone celebrates, everyone submits.

### Demo Order

The instructor will set the order. Each person gets 3 minutes:
- 30 sec: Problem
- 90 sec: Live demo
- 30 sec: Impact
- 30 sec: What's next

After all demos: vote for "Most Impactful" and "Most Creative"

### Submitting Your Project

After demos, submit your project to the team skills repository via Pull Request.

**What to submit:**
```
your-github-id/
├── PRD.md           (your project document)
└── skills/
    ├── main-skill/
    │   └── SKILL.md
    └── helper-skill/  (if you have one)
        └── SKILL.md
```

### Submission Steps (guided)

```bash
# 1. Make sure you're in the team repo
cd team-skills

# 2. Get the latest version
git checkout main && git pull origin main

# 3. Create your submission branch
git checkout -b project/your-github-id

# 4. Create your folder and copy files
mkdir -p your-github-id/skills
# (Claude will help copy your files)

# 5. Stage your files
git add your-github-id/

# 6. Commit
git commit -m "feat: your-github-id final project"

# 7. Push
git push origin project/your-github-id

# 8. Create Pull Request
gh pr create --title "Project: your-github-id" --body "## Project: [title]

- Skills: /skill-1, /skill-2
- Impact: [before] → [after]
- PRD: included"
```

Don't worry if this looks complex — Claude will walk you through each step.

## EXECUTE

### During demos:
- When it's your turn, present your 3-minute demo
- When others present, take notes on skills that could help YOUR work
- Vote for "Most Impactful" and "Most Creative"

### After demos, submit your project:

Ask Claude:
```
Help me submit my project to the team skills repository.
My GitHub ID is [your-id].
Walk me through each git step.
My project files are in [location].
```

Claude will guide you through cloning, branching, adding files, committing, pushing, and creating the PR.

### Camp Completion

After successful submission, you've completed the camp!

```
=== Camp Complete ===

You have:
✅ Installed Claude Code
✅ Mastered terminal basics
✅ Created your CLAUDE.md profile
✅ Connected your work tools via MCP
✅ Built custom skills
✅ Created multi-skill workflows
✅ Shipped a real project
✅ Submitted to the team repository

What's next:
→ Use your skills daily at work
→ Build new skills when you spot repetitive tasks
→ Help a colleague get started with Claude Code
→ Contribute improvements to the team skills repo
→ Join #claude-code on Slack for tips and support
```

## QUIZ

Final quiz — a reflection:

```
AskUserQuestion({
  "questions": [{
    "question": "What will you do FIRST on Monday morning with Claude Code?",
    "header": "Looking Forward",
    "options": [
      {"label": "Run my new skill on real work data", "description": ""},
      {"label": "Show a colleague what I built", "description": ""},
      {"label": "Build another skill for a different task", "description": ""},
      {"label": "All of the above!", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

All answers are correct! The point is that you're already thinking about using Claude Code in your real work. That means the camp worked.

End with:
```
The camp is over, but this is just the beginning.
You now have a skill that most people don't — you can build with AI.
Every repetitive task you spot is an opportunity for a new skill.
Every tool you use is a candidate for MCP connection.
Every workflow is a potential automation.

Welcome to the team that builds with AI.
```
