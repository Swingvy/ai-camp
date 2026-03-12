# Block 5: Multi-turn Problem Solving + Web Search

## EXPLAIN

Real work isn't one question and one answer. It's a conversation — you refine, redirect, and build on previous responses. Claude Code excels at this because it remembers everything within a session.

### Multi-turn Patterns

**Pattern 1: Start broad, then narrow**
```
You: "I need to prepare for tomorrow's client meeting"
Claude: (asks about client, creates agenda draft)
You: "Focus more on the pricing discussion"
Claude: (revises with pricing emphasis)
You: "Add our competitor comparison from last quarter"
Claude: (reads file, adds comparison)
```

**Pattern 2: Generate then refine**
```
You: "Draft a project proposal for automating our onboarding"
Claude: (creates full draft)
You: "The timeline is too aggressive. Make it 3 months instead of 1"
Claude: (adjusts timeline)
You: "Add a risk section"
Claude: (adds risks)
You: "Save as proposal-v1.md"
Claude: (saves)
```

**Pattern 3: Analyze then act**
```
You: "Read all the .csv files in this folder and tell me what's in them"
Claude: (reads and summarizes each file)
You: "Combine the sales data from Q1 and Q2 into one summary"
Claude: (merges and summarizes)
You: "Create a report with charts-ready data"
Claude: (creates formatted report)
```

### Key Techniques

| Technique | Example |
|-----------|---------|
| Course correct | "No, I meant the OTHER spreadsheet" |
| Add constraints | "Keep it under 200 words" |
| Change format | "Convert this to a table" |
| Undo | "Go back to the previous version" |
| Branch | "Save this, then try a completely different approach" |

### Web Search — Claude's Research Power

Claude Code can search the web to gather information and compile it into structured reports. This is incredibly powerful for research tasks:

```
You: "Research the top 5 project management tools for small teams.
      Compare pricing, key features, and user reviews.
      Create a comparison report as a markdown file."
Claude: (searches the web, compiles findings, creates report)
```

This would normally take you 30-60 minutes of browsing, reading, and formatting. Claude does it in seconds.

## EXECUTE

**Exercise 1: Multi-turn Conversation**

Bring a real work problem and solve it through conversation with Claude. Here are some starting points based on common roles:

**If you're in HR:**
```
I need to write a job posting for a [role]. Let's start with
the key responsibilities, then work on requirements, then
the company description. Help me draft each section.
```

**If you're in Marketing:**
```
I have a product launch next week. Help me create:
1. A press release draft
2. 3 social media post options
3. An internal announcement for Slack
Let's do them one at a time.
```

**If you're in Operations:**
```
I need to compare 3 vendors for our new [tool/service].
Help me create a comparison framework, then I'll give you
each vendor's details, and we'll build a recommendation.
```

**If you're in Finance:**
```
Help me build a monthly expense report template.
Start with categories, then add formatting, then create
a summary section with totals.
```

The goal: have at least a 5-turn conversation where you refine the output until it's genuinely useful for your work.

**Exercise 2: Web Search Report**

Now experience Claude's research power. Ask Claude to research a topic relevant to your work and create a structured report:

```
Research [your topic] using web search.
Compile the findings into a structured report with:
- Executive summary (3-4 sentences)
- Key findings (bullet points)
- Comparison table (if applicable)
- Recommendations
Save the report as research-report.md
```

Example topics by role:
- **HR**: "Best practices for remote onboarding in 2025"
- **Marketing**: "Top social media trends for B2B companies"
- **Sales**: "Sales enablement tools comparison"
- **Finance**: "Expense management software for small businesses"
- **Ops**: "Vendor evaluation frameworks"

Notice how Claude gathers information from multiple sources, organizes it, and produces a polished report — all in one request!

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What's the best approach when Claude's first response isn't quite right?",
    "header": "Multi-turn Quiz",
    "options": [
      {"label": "Start over with a completely new prompt", "description": ""},
      {"label": "Give up and do it manually", "description": ""},
      {"label": "Give feedback and refine: 'Make it shorter', 'Focus on X', 'Change the format to Y'", "description": ""},
      {"label": "Accept whatever Claude gives you", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Give feedback and refine"

If correct: "Exactly! Think of it as a collaboration. The first draft is just the starting point. The real value comes from refining — 'more detail here', 'simpler there', 'add this section'. That's how you get output that truly fits your needs."
If incorrect: "The power of Claude Code is the conversation. Don't start over — build on what you have. Say 'make it shorter', 'add more detail about X', 'change the format'. Each turn gets you closer to exactly what you need."
