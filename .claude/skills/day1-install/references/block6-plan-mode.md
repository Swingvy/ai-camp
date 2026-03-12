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

**Option 1: Use the /plan command**
```
/plan
```
Then describe your task.

**Option 2: Ask Claude to plan**
```
Plan how you would reorganize my project files
before you actually do anything. Show me the plan first.
```

### What You'll See

Claude will create a structured plan showing:
- What steps it will take
- What files it will read or modify
- What the expected outcome is

You then approve, adjust, or reject the plan before Claude executes.

## EXECUTE

Let's try Plan Mode with a simple task:

1. Activate Plan Mode by typing `/plan` or saying:

```
Plan how you would create a weekly task tracker for my team.
Don't execute yet — just show me the plan.
Include: what files you'd create, what structure they'd have,
and how I'd use them.
```

2. Review the plan Claude shows you
3. If you like it, tell Claude to proceed
4. If you want changes, tell Claude what to adjust

Try it now! The key is to see how Claude thinks through a problem before acting.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "When should you use Plan Mode?",
    "header": "Plan Mode Quiz",
    "options": [
      {"label": "For every single request, no matter how small", "description": ""},
      {"label": "Only when writing code", "description": ""},
      {"label": "For complex, multi-step tasks where you want to review the approach before execution", "description": ""},
      {"label": "Never — Claude always knows the best approach", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "For complex, multi-step tasks where you want to review the approach before execution"

If correct: "Right! Plan Mode is your safety net for big tasks. Simple questions don't need it, but when Claude is about to do something complex — like reorganizing files, building a report from multiple sources, or creating a multi-step workflow — it's smart to see the plan first."
If incorrect: "Plan Mode is best for complex tasks with multiple steps. For simple requests like 'what time is it?' or 'make this shorter,' you don't need it. But for bigger tasks — like creating a report from multiple sources or reorganizing a project — Plan Mode lets you review and approve the approach before Claude starts working."
