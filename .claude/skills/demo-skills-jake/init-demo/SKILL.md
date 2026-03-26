---
name: init-demo
description: "First-time setup for all morning skills. Seeds prefs files so morning-valet, weekly-news, my-jira-tickets, and standup-draft run without setup questions. Use for 'setup', 'init', 'initialize', 'first time', 'configure my skills'."
---

# Init Demo

## Steps

**Step 1: Check existing setup**
Check if `~/.claude/morning-valet-prefs.json` exists.
- If it does: ask "You're already set up. Reset all preferences?" — if No, stop.

**Step 2: Ask setup questions**
Use AskUserQuestion with all three questions at once:
- Q1: "Which industry are you in?" — options: SaaS / B2B Software · FinTech / Finance · HR Tech / People Ops · HealthTech · E-commerce · EdTech · Logistics · Other
- Q2: "What's your department?" — options: CEO / Executive · Sales · Marketing · Customer Success · Engineering · Product Management · QA
- Q3: "Which Jira statuses do you want to hide?" (multiselect) — options: Done · Closed · Cancelled · Released · QA Ready · Release Ready · In Review

**Step 3: Find standup channel**
Search Slack for a channel whose name contains "standup" or "stand-up" or "daily" using `slack_search_channels`.
Pick the best match and save its ID.

**Step 4: Write all prefs files**
Write these three files in one go:

`~/.claude/weekly-news-prefs.json`
```json
{ "industry": "[Q1 answer]", "department": "[Q2 answer]", "setup_complete": true }
```

`~/.claude/jira-ticket-prefs.json`
```json
{
  "exclude_statuses": [Q3 selections, defaults: "Done", "Closed", "Cancelled", "Released"],
  "exclude_self_moved": ["QA Ready"],
  "must_include_statuses": [],
  "setup_complete": true
}
```

`~/.claude/morning-valet-prefs.json`
```json
{ "setup_complete": true, "standup_channel_id": "[channel ID from Step 3]" }
```

**Step 5: Confirm**
```
✅ You're all set! Preferences saved.
   Industry:   [value]
   Department: [value]
   Jira hides: [values]
   Standup channel: #[channel name]

Run /morning-valet to start your day.
```
