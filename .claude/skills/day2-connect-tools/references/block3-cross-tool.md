# Block 3: Cross-tool Queries

## EXPLAIN

The real power of MCP isn't connecting one tool — it's connecting multiple tools and letting Claude work across them in a single conversation.

### What is a Cross-tool Query?

Instead of:
1. Open Slack → find messages → copy
2. Open Google Sheets → paste → format
3. Open Slack → post summary

You say:
```
"Collect customer complaints from #support this week,
 categorize them, put them in my tracking sheet,
 and post a summary to #team-updates"
```

Claude does steps 1-3 automatically.

### Cross-tool Query Examples by Role

**HR:**
```
"Check #hiring on Slack for interview feedback this week,
 summarize by candidate, and create a Google Doc report
 for the hiring committee"
```

**Marketing:**
```
"Find all mentions of our product launch in #marketing and #social,
 extract the key metrics mentioned, and add them to the
 campaign tracking sheet"
```

**Sales:**
```
"Look up {client name} in our CRM, find recent Slack conversations
 about them, and create a meeting prep brief as a Google Doc"
```

**Operations:**
```
"Compare our three vendor proposals from Google Drive,
 create a comparison table, and post the recommendation
 to #procurement"
```

**Finance:**
```
"Pull this month's expense receipts from the shared drive,
 categorize them, calculate totals by category, and
 update the budget tracking sheet"
```

### Tips for Good Cross-tool Queries

| Do | Don't |
|----|-------|
| Name specific channels/folders | Say "check everything" |
| Specify the time range | Leave it open-ended |
| Define the output format | Let Claude guess |
| Name the output location | Forget where to save |

### Example of a Well-structured Query

```
Read the last 7 days of messages in #customer-feedback on Slack.
Extract each piece of feedback with: customer name, topic, sentiment.
Create a Google Sheet with columns: Date, Customer, Topic, Sentiment, Raw Quote.
Sort by date (newest first).
Share the sheet link in #product-team with a 3-sentence summary.
```

## EXECUTE

Build a cross-tool query that would actually help your work:

1. Pick 2 tools you connected (or will connect)
2. Think of a real task where you currently switch between them
3. Write the query in plain language
4. Run it in Claude Code

Template to help you structure it:
```
Read [what data] from [Tool 1] for [time period].
Process it by [grouping/filtering/summarizing].
Output to [Tool 2] in [specific format].
[Optional: notify someone in Tool 3].
```

Try your query now. If something doesn't work, refine it — this is exactly the kind of iteration we practiced on Day 1.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What makes a cross-tool query effective?",
    "header": "Cross-tool Quiz",
    "options": [
      {"label": "Using as many tools as possible", "description": ""},
      {"label": "Keeping it vague so Claude has flexibility", "description": ""},
      {"label": "Being specific: name the source, time range, format, and destination", "description": ""},
      {"label": "Always starting with Google Drive", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Being specific: name the source, time range, format, and destination"

If correct: "Right! The more specific you are, the better the result. Always tell Claude: WHERE to read from, WHAT time range, HOW to format it, and WHERE to put the output."
If incorrect: "Effective cross-tool queries are specific. Tell Claude exactly: (1) where to read from, (2) what time range, (3) how to format the output, and (4) where to save it. Vague queries lead to vague results."
