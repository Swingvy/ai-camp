# Block 1: Guided Build Sprint

## EXPLAIN

This is the longest block — a 90-minute guided build session. You build, I coach.

### Build Rhythm

```
[0:00 - 0:10]  Set up project structure
[0:10 - 0:40]  Build core skill (the main automation)
[0:40 - 0:50]  First test + fix
[0:50 - 1:10]  Build secondary skill or enhance (if time)
[1:10 - 1:20]  Full workflow test
[1:20 - 1:30]  Final fixes + polish
```

### Step 1: Project Structure

```bash
mkdir -p my-project/.claude/skills/my-skill
```

Files you'll create:
```
my-project/
├── CLAUDE.md              (project context)
├── .claude/
│   └── skills/
│       ├── main-skill/
│       │   └── SKILL.md   (your primary skill)
│       └── helper-skill/
│           └── SKILL.md   (optional second skill)
└── output/                (where results go)
```

### Step 2: Build Your Core Skill

Use everything you've learned:
- **Day 3**: SKILL.md anatomy (frontmatter, steps, output format, error handling)
- **Day 4**: Subagents (parallel fetch), chaining (connect skills), hooks (auto-actions)

Write your SKILL.md with clear:
- Steps (numbered, specific)
- Output format (literal template)
- Error handling (what if things go wrong)

### Step 3: Test Aggressively

Run it 3 times:
1. **Happy path**: normal conditions, expected data
2. **Edge case**: what if there's no data? Empty channels? No files?
3. **Real data**: use actual work data, not test data

### Coaching Available

During the build, ask me anything:
- "How do I make this skill read from Slack AND Google Drive?"
- "My skill gives different output each time — how do I fix it?"
- "I want to add a second skill that processes the first one's output"
- "Something's broken and I don't know why"

I'm here to unblock you. Don't spend more than 5 minutes stuck — ask for help.

## EXECUTE

Start building. Follow the rhythm above:

1. **Set up structure** (10 min)
   - Create project folder and skill directories
   - Set up CLAUDE.md with project context

2. **Build core skill** (30 min)
   - Write your SKILL.md
   - Include all sections: steps, output format, error handling
   - Use subagents if fetching from multiple sources

3. **Test and fix** (10 min)
   - Run your skill
   - Check output against expectations
   - Fix issues in SKILL.md

4. **Enhance or add second skill** (20 min)
   - Option A: Add more features to your core skill
   - Option B: Build a second skill that chains with the first

5. **Full workflow test** (10 min)
   - Run the complete workflow start to finish
   - With real (or realistic) data

6. **Polish** (10 min)
   - Clean up output format
   - Add any missing error handling
   - Make sure it's demo-ready

Go! Start with step 1 now.

## QUIZ

No quiz for this block — the build IS the test. Move to Block 2 when your project is working.
