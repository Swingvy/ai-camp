# Block 6: Introduction to Plan Mode

## EXPLAIN

When you give Claude a complex task, it sometimes jumps straight into action. But for bigger tasks, it's better to have Claude **plan first, then execute**. That's what **Plan Mode** does.

### What is Plan Mode?

Plan Mode tells Claude: "Don't do anything yet — just think about HOW you would do it, and show me the plan first."

### Why Use Plan Mode?

| Without Plan Mode | With Plan Mode |
|-------------------|---------------|
| Claude jumps straight into action | Claude shows you the plan first |
| You might not like the approach | You can review and adjust before anything happens |
| Harder to course-correct mid-task | You approve each step before execution |
| Risky for complex tasks | Safe for complex tasks |

### When to Use Plan Mode

- Multi-step tasks (more than 3 steps)
- Tasks where you're not sure about the approach
- Tasks that touch important files or data
- When you want to understand what Claude will do before it does it

### How to Activate Plan Mode

In the **Claude Desktop App**, simply ask Claude to plan before acting. Use phrases like:

**Example 1: Direct request**
```
Before you do anything, plan out the steps first.
I want to create a weekly report from my Slack messages and Jira tickets.
Show me your plan before executing.
```

**Example 2: Review before action**
```
Plan how you would reorganize my project files.
Don't execute yet — just show me the plan first.
```

**Example 3: Step-by-step approval**
```
I need to create onboarding documents for new hires.
Walk me through your plan step by step.
I'll approve each step before you proceed.
```

> **Tip:** The key phrases are **"plan first"**, **"show me the plan"**, **"don't execute yet"**, and **"before you do anything"**. These tell Claude to think before acting.

### What You'll See

Claude will create a structured plan showing:
- What steps it will take
- What files it will read or modify
- What the expected outcome is

You then approve, adjust, or reject the plan before Claude executes.

## EXECUTE

Let's try Plan Mode with a simple task. Type this in your Claude Desktop App:

```
Before you do anything, plan out the steps first.
I want to create a weekly task tracker for my team.
Show me your plan including:
- What files you'd create
- What structure they'd have
- How I'd use them
Don't execute until I approve the plan.
```

Then:
1. Review the plan Claude shows you
2. If you like it, tell Claude to proceed
3. If you want changes, tell Claude what to adjust

Try it now! The key is to see how Claude thinks through a problem before acting.

---
👆 Try this yourself now.
When you're done, type **"next"** or **"quiz"** to continue.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "How do you activate Plan Mode in the Claude Desktop App?",
    "header": "Plan Mode Quiz",
    "options": [
      {"label": "Ask Claude to 'plan first' or 'show me the plan before executing'", "description": ""},
      {"label": "Click a Plan Mode button in the toolbar", "description": ""},
      {"label": "Type /plan in the chat", "description": ""},
      {"label": "It's always on by default", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Ask Claude to 'plan first' or 'show me the plan before executing'"

If correct: "Right! In the Desktop App, you activate Plan Mode by asking Claude in natural language — say things like 'plan first', 'show me the plan', or 'don't execute yet'. Claude will lay out the steps and wait for your approval before doing anything."
If incorrect: "In the Desktop App, Plan Mode is activated by asking Claude in plain language. Say things like **'plan first'**, **'show me the plan before executing'**, or **'don't execute yet'**. Claude understands these as instructions to plan before acting."
