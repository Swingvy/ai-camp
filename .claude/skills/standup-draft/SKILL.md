---
name: standup-draft
description: "Generate a daily standup draft from Jira and Slack activity. Use for 'standup', 'daily standup', 'write my standup', 'what did I do yesterday', 'scrum update'."
---

# Daily Standup Draft

## What this skill does
Generates a ready-to-paste standup update by pulling what you actually did from
Jira and Slack — no more staring at a blank screen trying to remember yesterday.

## Steps

**Step 1: Fetch yesterday's Jira activity**
Query Jira for tickets updated or transitioned by the current user yesterday:
- JQL: `assignee = currentUser() AND updated >= -1d ORDER BY updated DESC`
- Look for: status changes, comments added, tickets closed or moved to QA Ready/In Review
- On Mondays, look back across Friday + the weekend: `updated >= -3d`

**Step 2: Fetch today's Jira tickets**
Query for tickets currently in progress or to be started today:
- JQL: `assignee = currentUser() AND sprint in openSprints() AND status IN ("In Progress", "To Do", "Open", "Backlog") ORDER BY updated DESC`

**Step 3: Read yesterday's standup thread**
Fetch recent messages from the standup Slack channel (ID: `C017BR4KUPL`) using `slack_get_channel_history`.
- Look for a message posted by the current user yesterday (or Friday if today is Monday)
- If found, read any thread replies on that message using `slack_get_thread_replies`
- Use this context to:
  - Cross-check what the user said they'd do yesterday vs. what actually happened in Jira
  - Pick up any team comments or follow-ups from the thread that are relevant today

**Step 4: Check for blockers**
Look for:
- Any Jira tickets with status "Blocked"
- Any Slack direct mentions from yesterday that have not been replied to (use `slack_search_public_and_private` with the current user's name and yesterday's date)

**Step 5: Generate the standup draft**
Format the output using the team's standup form — 6 sections, bullet points, plain language:

```
📝 Standup Draft — {today's date}

1. Today, I'm [emoji]

2. Done
• [Action verb] [ticket ID] [ticket title]
• (If nothing: leave blank)

3. Delayed
• [ticket ID] [ticket title] — [brief reason]
• (If nothing: leave blank)

4. Todo today
• [ticket ID] [ticket title]
• (If nothing: "No open tickets assigned — check with team.")

5. Blockage
• [ticket ID] [ticket title] — [brief reason]
• (If none: leave blank)

6. ETC
• [anything else worth mentioning — meetings, OOO, notes]
• (If nothing: leave blank)
```

Use plain, natural language. Keep each bullet to one line.
Action verbs to use: Completed, Moved to QA, Reviewed, Fixed, Updated, Started, Commented on, Closed.
For "Today, I'm" — pick an appropriate emoji based on workload (🙂 normal, 😅 busy, 😴 slow day, etc.).

**Step 6: Ask if the user wants to post it**
After showing the draft, ask:
"Post this to Slack? (yes / no — it will be posted to the standup channel)"
- If yes → post the draft as a new message to channel `C017BR4KUPL`
- If no → display the draft cleanly so the user can copy-paste it themselves

## Output format

```
📝 Standup Draft — Wednesday, March 26 2026

1. Today, I'm 🙂

2. Done
• Moved LV-959 (Story 3-3, termination date modification) to QA Ready
• Completed CS-6050 (Cannot approve payroll - #14470)

3. Delayed

4. Todo today
• LV-968 [QA] Story 3-1b — Re-visit story 1-3
• MP-1587 Regression test (Mobile)

5. Blockage

6. ETC

---
Post to Slack? (yes / no)
```

## Error handling
- If Jira MCP is not connected: "Jira is not connected. Writing standup from Slack activity only."
- If no Jira activity found for yesterday: show "No Jira activity recorded yesterday." and continue
- If Slack is not connected: skip the blocker check and the posting option; note "Slack not connected — copy and paste manually."
- If it's Monday: automatically look back to Friday and note "(Friday's activity)" next to yesterday's items
