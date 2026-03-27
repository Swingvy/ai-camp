# Morning — 晨間工作準備總覽

## Problem
> A sales rep spends 10–30 minutes every morning switching between Gmail, HubSpot, and Google Calendar before she can start selling.

- **Current state**: Every morning, Cindy manually checks unread client emails in Gmail, pulls up the HubSpot follow-up list, and finds an open slot in Google Calendar to block for calls — across 3 separate tools, taking 10–30 minutes before real work begins.
- **Desired state**: Type one command → get a complete morning briefing (emails + call list + calendar slots) in under 60 seconds, without switching tabs.
- **Success criteria**: Morning prep time reduced from 10–30 minutes to under 2 minutes, every workday.

## Skills

| # | Skill name | Description | Status |
|---|-----------|-------------|--------|
| 1 | `/morning` | Chains all 3 parts: email triage → call list → calendar blocking | Working |
| 2 | `/mail-check` | Gmail → sorted unread client emails by time period | Working |
| 3 | `/call-prep` | HubSpot → today's follow-up list with deal stage & notes | Working |
| 4 | `/call-block` | Google Calendar → auto-schedules 2 call slots (AM + PM) | Working |
| 5 | `/callcold` | HubSpot → clients not contacted in 7–21 days to re-engage | Working |
| 6 | `/client-research` | Web + HubSpot + Gmail → prospect summary before meetings | Working |

## MCP Connections Used
- **Gmail**: Reads unread client emails (Part 1 of `/morning`)
- **HubSpot**: Reads deal stage, contact info, last contact date (Part 2 of `/morning`)
- **Google Calendar**: Reads schedule and creates call-block events (Part 3 of `/morning`)

## How to Use
1. Open Claude in the morning
2. Type `早安`, `morning`, or `好早`
3. Claude automatically runs all 3 parts in sequence:
   - Part 1: Sorted unread client emails (by today / yesterday / this week / 2 weeks)
   - Part 2: Today's HubSpot call follow-up list
   - Part 3: 2 call-block events created in Google Calendar with the client list in the description
4. For cold leads: type `冷單`
5. Before a client meeting: type `查XX公司`

## Impact
- **Before**: 10–30 minutes of manual tab-switching across Gmail, HubSpot, and Google Calendar every morning
- **After**: Under 2 minutes — one command, everything ready, calendar blocked
