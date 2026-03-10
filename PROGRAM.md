# Claude Code Internal Training Camp

> 5 days to permanently change how every team member works.

A hands-on training camp for non-engineers to master Claude Code — from first install to building production workflows.

---

## Program Overview

| Item | Detail |
|------|--------|
| Duration | 5 days (Mon–Fri), 3 hours/day |
| Target | Non-engineers: Ops, HR, Finance, Marketing, Sales, CS, Legal, PM |
| Class Size | 8–15 per cohort (for hands-on support) |
| Prerequisites | Mac or Windows laptop, company email, basic typing skills |
| Outcome | Each participant ships at least 1 working skill/workflow that solves a real job problem |

---

## Daily Schedule Structure

Each day follows the same rhythm:

```
[0:00 – 0:20]  Warm-up: Review yesterday + Q&A
[0:20 – 1:00]  Concept: Learn new capability (with live demo)
[1:00 – 1:10]  Break
[1:10 – 2:30]  Hands-on: Build something real
[2:30 – 3:00]  Share & Reflect: Show what you built, daily journal
```

---

## Day 1: Install & First Conversations

### Goal
Everyone has Claude Code running and can hold a productive conversation.

### Concept (40 min)

**1. What is Claude Code?**
- Not a chatbot — a CLI agent that reads, writes, and executes
- Why terminal? (speed, automation, no copy-paste, direct file access)
- Live demo: solve a real task in 2 minutes that normally takes 30

**2. Installation**

| Step | Command | Notes |
|------|---------|-------|
| Install Node.js | `brew install node` (Mac) / download from nodejs.org (Windows) | v18+ required |
| Install Claude Code | `npm install -g @anthropic-ai/claude-code` | One command |
| First launch | `claude` | Opens interactive session |
| Auth | Follow browser prompt | Anthropic account or API key |

**3. Terminal Basics (for non-engineers)**

| What you want to do | Command | Translation |
|---------------------|---------|-------------|
| See where I am | `pwd` | "What folder am I in?" |
| See what's here | `ls` | "Show me the files" |
| Go to a folder | `cd Desktop` | "Open this folder" |
| Go back up | `cd ..` | "Go to parent folder" |
| Create a folder | `mkdir my-project` | "Make a new folder" |
| Clear the screen | `clear` | "Clean up" |

### Hands-on (80 min)

**Exercise 1: First Conversation**
- Launch Claude Code in a new project folder
- Ask Claude to create a simple file (e.g., "Create a weekly schedule template for my team")
- Review what Claude created, ask for modifications

**Exercise 2: CLAUDE.md — Teaching Claude About You**
- Create a `CLAUDE.md` file that describes:
  - Your role and team
  - Tools you use daily (Slack, Notion, Google Sheets, etc.)
  - Your common tasks
  - Your preferences (language, format, style)
- Test: Ask Claude something about your work and see how CLAUDE.md changes the response

**Exercise 3: Multi-turn Problem Solving**
- Bring a real work problem (e.g., "I need to summarize 50 customer complaints")
- Work with Claude through multiple turns to solve it
- Practice: giving context, being specific, correcting course

### Daily Journal
```
What surprised me:
What confused me:
One thing I want to try tomorrow:
```

---

## Day 2: Connect Your Tools (MCP)

### Goal
Claude Code is connected to Slack, Google Drive, Notion, or whatever tools each person uses daily.

### Concept (40 min)

**1. What is MCP (Model Context Protocol)?**
- Think of it as "plugins" for Claude Code
- Claude can read from and write to external tools
- No coding required — just configuration

**2. How MCP Works**
```
You ──→ Claude Code ──→ MCP Server ──→ Your Tool
         "Get my latest            Slack / Notion /
          Slack messages"          Google Drive / etc.
```

**3. Available MCP Servers (pick what you use)**

| Tool | MCP Server | What it enables |
|------|-----------|-----------------|
| Slack | `@anthropic/slack-mcp` | Read channels, send messages, search history |
| Google Drive | `@anthropic/gdrive-mcp` | Read/create docs, sheets, slides |
| Notion | `notion-mcp-server` | Read/update pages, databases |
| GitHub | `@anthropic/github-mcp` | Issues, PRs, code search |
| Linear | `linear-mcp-server` | Issue tracking, project management |
| Figma | `figma-mcp-server` | Read designs, extract specs |
| Calendar | `google-calendar-mcp` | Read/create events |
| File System | `@anthropic/filesystem-mcp` | Read/write local files safely |
| Web | `@anthropic/web-mcp` | Fetch and read web pages |

### Hands-on (80 min)

**Exercise 1: Install Your First MCP Server**
```bash
# Example: Slack
claude mcp add slack -- npx -y @anthropic/slack-mcp

# Example: Google Drive
claude mcp add gdrive -- npx -y @anthropic/gdrive-mcp
```
- Each participant installs 1–2 MCP servers for their most-used tools
- Verify: "Claude, show me my latest Slack messages from #general"

**Exercise 2: Cross-tool Queries**
- "Summarize the last week of #product-feedback on Slack and create a Google Doc report"
- "Find all open issues assigned to me on Linear and post a status update to Slack"
- Each person designs a query that spans 2 of their connected tools

**Exercise 3: Troubleshooting Workshop**
- Common issues: auth tokens, permissions, server not starting
- How to check: `claude mcp list`, `claude mcp logs`
- Buddy system: pair up and help each other debug

### Homework
Connect at least 2 more tools before tomorrow. Write down 3 things you wish Claude could do across your tools.

---

## Day 3: Build Your First Skill

### Goal
Each participant creates a reusable Claude Code Skill that automates a repetitive task.

### Concept (40 min)

**1. What is a Skill?**
- A reusable prompt template that Claude follows
- Saved as a `SKILL.md` file in `.claude/skills/`
- Invoked with `/skill-name` — like a custom command
- Not code — just structured instructions in plain language

**2. Anatomy of a Skill**

```markdown
---
name: weekly-report
description: Generate a weekly status report from Slack and Linear.
  Use when asked for "weekly report", "status update", or "weekly summary".
---

# Weekly Status Report Generator

## What this skill does
Collects updates from Slack channels and Linear issues,
then produces a formatted weekly report.

## Steps
1. Fetch messages from #team-updates (last 7 days)
2. Fetch completed Linear issues (last 7 days)
3. Summarize into sections: Completed, In Progress, Blocked
4. Format as markdown with bullet points
5. Save to `reports/week-{date}.md`

## Output format
(define exactly what the output should look like)
```

**3. Good Skill = Good Prompt**

| Principle | Bad | Good |
|-----------|-----|------|
| Be specific | "Make a report" | "Fetch Slack messages from #sales for the past 7 days, extract customer names and issues mentioned, group by issue type" |
| Define output | (nothing) | "Output as a markdown table with columns: Customer, Issue, Date, Status" |
| Handle edge cases | (nothing) | "If no messages found, output: 'No updates this week'" |
| Set boundaries | (nothing) | "Do NOT send any messages. Read-only." |

### Hands-on (80 min)

**Exercise 1: Identify Your Repetitive Task**
Each participant answers:
- What task do you do every day/week that follows the same pattern?
- What inputs does it need? What output does it produce?
- How long does it take you manually?

Common examples by role:

| Role | Skill idea |
|------|-----------|
| HR | `/onboarding-checklist` — Generate personalized onboarding docs for new hires |
| Finance | `/expense-summary` — Summarize expense reports from shared drive |
| Marketing | `/social-draft` — Draft social media posts from product updates |
| Sales | `/deal-brief` — Compile customer info before a sales call |
| CS | `/ticket-summary` — Summarize support tickets by category |
| Ops | `/vendor-compare` — Compare vendor proposals side by side |
| PM | `/sprint-recap` — Generate sprint recap from Linear/Jira |
| Legal | `/contract-review` — Extract key terms from contract drafts |

**Exercise 2: Write Your Skill**
- Create `.claude/skills/your-skill-name/SKILL.md`
- Follow the anatomy template
- Include: name, description, steps, output format, error handling

**Exercise 3: Test & Iterate**
- Run your skill: `/your-skill-name`
- Does it produce the right output?
- Refine: add missing steps, clarify instructions, fix edge cases
- Pair up: test each other's skills and give feedback

### Share (30 min)
Each participant demos their skill to the group (2 min each).

---

## Day 4: Advanced Skills & Workflows

### Goal
Level up skills with subagents, multi-step workflows, and team sharing.

### Concept (40 min)

**1. Subagents — Divide and Conquer**
- A skill can launch background agents to work in parallel
- Example: Fetch Slack data AND Linear data at the same time, then combine
- Use the Agent tool inside your skill instructions

**2. Chaining Skills — Workflows**
- Skill A outputs → Skill B takes as input
- Example: `/collect-feedback` → `/analyze-sentiment` → `/draft-response`

**3. Hooks — Automatic Triggers**
- Run actions automatically when Claude does something
- Example: auto-format every file Claude creates
- Example: validate output before saving

**4. Sharing Skills Across the Team**
- Skills live in `.claude/skills/` — shareable via git
- Team repository: everyone contributes skills, everyone benefits
- Version control: skills improve over time

### Hands-on (80 min)

**Exercise 1: Enhance Yesterday's Skill**
Choose one upgrade:
- Add parallel data fetching (subagent)
- Add input validation (check before running)
- Add output formatting (professional-looking results)
- Add error messages (graceful failures)

**Exercise 2: Build a Two-Skill Workflow**
Create a second skill that works with your first:

| First skill | Second skill | Workflow |
|-------------|-------------|----------|
| `/collect-data` | `/make-report` | Gather → Summarize |
| `/draft-email` | `/review-tone` | Write → Polish |
| `/scan-tickets` | `/prioritize` | Collect → Rank |
| `/meeting-notes` | `/action-items` | Capture → Extract |

**Exercise 3: Team Skill Repository**
- Set up a shared git repo for team skills
- Each person contributes their skill via PR
- Practice: clone, add your skill, commit, push, create PR
- (Guided step-by-step for non-engineers)

### Share (30 min)
Demo your workflow (Skill A → Skill B) to the group.

---

## Day 5: Ship Your Project

### Goal
Each participant delivers a complete, working solution that improves their actual job.

### Morning: Project Sprint (2 hours)

**The Brief:**
Build one of the following (or propose your own):

| Project type | Example | Deliverable |
|-------------|---------|-------------|
| **Workflow automation** | Weekly reporting pipeline | 2–3 connected skills that automate a weekly task |
| **Internal tool** | Team dashboard generator | A skill that produces a formatted status page |
| **Content system** | Marketing content pipeline | Skills for drafting, reviewing, and publishing |
| **Data pipeline** | Customer feedback analyzer | Skills that collect, process, and visualize data |
| **Process improvement** | Onboarding automation | Skills that generate checklists, docs, and notifications |

**Project requirements:**
- Solves a real problem from your actual job
- Uses at least 1 MCP connection (external tool)
- Has at least 1 custom skill
- Includes a brief PRD (Problem, Solution, How to use)

**Support structure:**
- Instructors circulate to unblock issues
- Buddy system continues (help each other)
- Quick wins encouraged — ship something small that works, then improve

### Afternoon: Demo Day (1 hour)

**Presentation format (3 min per person):**
1. **Problem** (30 sec): What was painful before?
2. **Demo** (1.5 min): Show it working live
3. **Impact** (30 sec): Time saved, errors reduced, quality improved
4. **What's next** (30 sec): How will you expand this?

**Celebration:**
- Vote for "Most Impactful" and "Most Creative"
- Certificates of completion
- All projects merged into team skills repository

---

## Post-Camp: Sustaining the Change

### Week 1 After Camp
- [ ] Use Claude Code for at least 1 real task per day
- [ ] Refine your skills based on real usage
- [ ] Share tips in #claude-code Slack channel

### Month 1 After Camp
- [ ] Build 2 more skills for your role
- [ ] Help a colleague get started
- [ ] Submit improvement PRs to team skills repo

### Ongoing
- [ ] Monthly "Skill Share" sessions (30 min, 3 demos)
- [ ] Team skills repo maintained and growing
- [ ] New hire onboarding includes Claude Code setup

---

## Instructor Preparation Checklist

### Before Camp

| Task | When | Owner |
|------|------|-------|
| Set up Anthropic org account with enough seats | 2 weeks before | Admin |
| Pre-install Node.js on all participant laptops | 1 week before | IT |
| Create team GitHub repo for shared skills | 1 week before | Instructor |
| Set up #claude-code Slack channel | 1 week before | Instructor |
| Prepare MCP auth tokens (Slack, Google, etc.) | 3 days before | IT + Admin |
| Test full install flow on company network | 3 days before | Instructor |
| Collect participant role + daily tools survey | 1 week before | Instructor |
| Prepare fallback hotspot (in case of network issues) | 1 day before | Instructor |

### Participant Pre-survey

Send this 1 week before camp:

```
1. Your name and team:
2. Your role (what do you do day-to-day?):
3. Tools you use daily (check all):
   [ ] Slack  [ ] Notion  [ ] Google Workspace  [ ] Linear
   [ ] Jira   [ ] Figma   [ ] Salesforce  [ ] HubSpot
   [ ] Other: ___
4. One repetitive task you wish was automated:
5. Comfort level with terminal/command line (1-5):
6. Have you used any AI tools before? Which ones?
```

### Contingency Plans

| Issue | Solution |
|-------|----------|
| Participant can't install | Pre-built VM / cloud workspace as backup |
| MCP server won't connect | Prepared mock data files as fallback |
| Network issues | Local-first exercises, offline skill writing |
| Participant falls behind | Buddy system + instructor 1:1 during exercises |
| Participant is too advanced | Challenge tasks: build skills for others, help neighbors |

---

## Success Metrics

| Metric | Target | How to measure |
|--------|--------|----------------|
| Installation rate | 100% | Everyone has Claude Code running by Day 1 end |
| MCP connections | 2+ per person | Check `.claude.json` configs on Day 2 |
| Skills created | 2+ per person | Count files in `.claude/skills/` on Day 5 |
| Project shipped | 1 per person | Demo Day presentations on Day 5 |
| Post-camp usage | 3x/week | Self-reported in weekly check-in (Month 1) |
| Skills shared | 5+ in team repo | Count PRs in team skills repo (Month 1) |
| NPS | 8+ | Post-camp survey |

---

## Appendix: Quick Reference Card

Give this to every participant on Day 1:

```
╔══════════════════════════════════════════════════════════╗
║              CLAUDE CODE QUICK REFERENCE                 ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  START          claude                                   ║
║  EXIT           /exit  or  Ctrl+C                        ║
║  CLEAR          /clear                                   ║
║  HELP           /help                                    ║
║                                                          ║
║  SKILLS         /skill-name     (run a skill)            ║
║  MCP LIST       claude mcp list (see connections)        ║
║  MCP ADD        claude mcp add name -- command           ║
║                                                          ║
║  TIPS                                                    ║
║  • Be specific: "summarize Q4 sales from sheet X"        ║
║  • Give context: "I'm preparing for a board meeting"     ║
║  • Iterate: "make it shorter" / "add more detail"        ║
║  • Say no: "don't modify that file" / "read only"        ║
║                                                          ║
║  FILES                                                   ║
║  CLAUDE.md            = Your profile (Claude reads this) ║
║  .claude/skills/      = Your custom commands             ║
║  .claude.json         = MCP connections config           ║
║                                                          ║
║  EMERGENCY                                               ║
║  Ctrl+C               = Stop current action              ║
║  /clear               = Fresh start                      ║
║  Ask in #claude-code   = Get help from teammates         ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```
