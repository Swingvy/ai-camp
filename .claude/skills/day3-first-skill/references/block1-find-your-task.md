# Block 1: Find Your Repetitive Task

## EXPLAIN

The best skill solves a problem you actually have. Let's find yours.

### The 3 Questions

1. **What do you do repeatedly?** (daily, weekly, monthly)
2. **Does it follow a pattern?** (same steps each time)
3. **Could you explain it to a new colleague?** (if yes, you can explain it to Claude)

If you answered yes to all 3, it's a great skill candidate.

### How to Spot a Good Candidate

| Good skill candidate | Bad skill candidate |
|---------------------|---------------------|
| Same steps every time | Different every time |
| Takes 10+ minutes | Takes 30 seconds |
| Has clear input & output | Requires lots of judgment |
| Uses tools Claude can access | Requires physical actions |
| You do it regularly | You did it once |

### Ideas by Role

| Role | Repetitive task | Skill name | Time saved |
|------|----------------|------------|------------|
| HR | Write onboarding checklists for new hires | `/onboarding-pack` | 1 hr/hire |
| HR | Compile interview feedback from multiple interviewers | `/interview-summary` | 30 min/candidate |
| Finance | Categorize expenses from receipts | `/expense-categorize` | 2 hr/month |
| Finance | Generate monthly budget vs. actual report | `/budget-report` | 1 hr/month |
| Marketing | Draft social media posts from blog posts | `/social-from-blog` | 20 min/post |
| Marketing | Compile campaign performance across platforms | `/campaign-report` | 1 hr/week |
| Sales | Research a prospect before a call | `/prospect-brief` | 15 min/call |
| Sales | Summarize a deal after meeting | `/deal-summary` | 10 min/meeting |
| CS | Categorize support tickets by issue type | `/ticket-triage` | 30 min/day |
| CS | Draft response templates for common issues | `/response-draft` | 10 min/ticket |
| Ops | Compare vendor proposals | `/vendor-compare` | 2 hr/comparison |
| PM | Generate sprint status from project tool | `/sprint-status` | 30 min/sprint |
| Legal | Extract key terms from contracts | `/contract-extract` | 1 hr/contract |

### Task Decomposition

Once you pick a task, break it into:

```
INPUT:   What information do you start with?
PROCESS: What steps do you follow?
OUTPUT:  What do you produce at the end?
```

Example:
```
Task: Weekly team status report
INPUT:   Slack messages from #team-updates (last 7 days)
PROCESS: Group by project → summarize each → note blockers
OUTPUT:  Markdown report with sections per project
```

## EXECUTE

1. Look at your automation ideas from yesterday (Day 2 homework: `automation-ideas.md`)
2. Pick ONE task — the one that's:
   - Most repetitive
   - Most annoying
   - Clearest pattern

3. Fill in this template (write it down or tell me):

```
TASK NAME: _______________
HOW OFTEN: daily / weekly / monthly / per-event
TIME IT TAKES: ___ minutes

INPUT:   What do I start with?
         _______________

PROCESS: What steps do I follow?
         Step 1: _______________
         Step 2: _______________
         Step 3: _______________

OUTPUT:  What do I produce?
         _______________

TOOLS INVOLVED: Slack / Notion / Google Drive / etc.
         _______________
```

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "Which task is the BEST candidate for a Claude Code Skill?",
    "header": "Task Selection Quiz",
    "options": [
      {"label": "Negotiating a deal with a client (requires intuition and relationship)", "description": ""},
      {"label": "Compiling a weekly status report from Slack messages (same steps every week)", "description": ""},
      {"label": "Deciding which candidates to invite for interviews (requires deep judgment)", "description": ""},
      {"label": "Having a 1-on-1 conversation with a team member (interpersonal)", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Compiling a weekly status report from Slack messages (same steps every week)"

If correct: "Yes! It's repetitive, follows the same steps, has clear input (Slack messages) and output (report), and uses a tool Claude can access via MCP. The other options require human judgment and interpersonal skills that can't be automated."
If incorrect: "The weekly status report is the best candidate because: (1) it's repetitive, (2) same steps every time, (3) clear input (Slack) and output (report), (4) Claude can access Slack via MCP. Tasks requiring judgment, intuition, or interpersonal interaction aren't good skill candidates."
