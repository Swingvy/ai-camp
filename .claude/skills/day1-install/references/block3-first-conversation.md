# Block 3: First Real Conversation

## EXPLAIN

Now that Claude Code is running, let's have a real conversation. The key difference from chatbots: Claude Code can actually DO things on your computer.

### 3 Types of Requests

| Type | Example | What Claude does |
|------|---------|-----------------|
| **Ask** | "What files are in this folder?" | Reads and reports |
| **Create** | "Write a meeting agenda for tomorrow" | Creates a file |
| **Transform** | "Take this data and make a summary" | Reads → processes → writes |

### Tips for Good Conversations

1. **Be specific** — "Summarize Q4 sales data" beats "Help me with sales"
2. **Give context** — "I'm preparing for a board meeting next Tuesday"
3. **Iterate** — "Make it shorter" / "Add a section about budget" / "Use bullet points instead"
4. **Set boundaries** — "Don't delete anything" / "Read only, don't modify"

### Understanding Claude's Actions

When Claude wants to do something (read a file, create a file, run a command), it will ask for your permission. You'll see options like:

- **Allow** — let Claude do this one action
- **Allow always** — let Claude do this type of action without asking again
- **Deny** — don't let Claude do this

Start by reviewing each action. As you get comfortable, you can allow more freely.

## EXECUTE

Launch Claude Code in your `claude-camp` folder and try these 3 conversations:

**Conversation 1: Ask**
```
What is my current working directory, and what files exist here?
```

**Conversation 2: Create**
```
Create a file called "my-tasks.md" with a weekly task template.
Include sections for Monday through Friday, each with checkboxes for:
- Morning standup notes
- Key tasks for the day
- End of day summary
```

**Conversation 3: Transform**
```
Read the my-tasks.md file you just created and convert it into
a more compact format — one table with columns: Day, Priority Task,
Notes. Save it as "my-tasks-compact.md"
```

After each conversation, check the files Claude created:
```bash
ls
cat my-tasks.md
cat my-tasks-compact.md
```

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What makes Claude Code different from a regular chatbot?",
    "header": "Conversation Quiz",
    "options": [
      {"label": "It gives better answers", "description": ""},
      {"label": "It can read, write, and execute actions on your computer", "description": ""},
      {"label": "It's faster", "description": ""},
      {"label": "It has more knowledge", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "It can read, write, and execute actions on your computer"

If correct: "Exactly! A chatbot just talks. Claude Code can actually create files, read your data, connect to your tools, and take action. That's the game changer."
If incorrect: "The key difference is action. Regular chatbots only talk. Claude Code can read files, create documents, run commands, and connect to your tools. It doesn't just suggest — it does."
