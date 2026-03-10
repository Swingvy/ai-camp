# Block 3: Hooks — Automatic Triggers

## EXPLAIN

A **hook** is a command that runs automatically when Claude does something. Think of it as an automatic reaction.

### The Concept

```
Claude creates a file  →  Hook automatically runs  →  "File created at reports/weekly.md"
Claude finishes a task  →  Hook automatically runs  →  Notification sent
```

You don't have to remember to do these checks — they happen on their own.

### Types of Hooks

| Hook | When it fires | Use case |
|------|--------------|----------|
| `PreToolUse` | Before Claude uses a tool | Validate or block certain actions |
| `PostToolUse` | After Claude uses a tool | Log, notify, or post-process |
| `Notification` | When Claude wants your attention | Send alerts to Slack or other channels |
| `Stop` | When Claude finishes | Run cleanup or final checks |

### How to Set Up Hooks

Hooks are configured in your settings. You can add them at the project level:

```json
// .claude/settings.json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write",
        "hooks": [
          {
            "type": "command",
            "command": "echo 'File written: $CLAUDE_TOOL_INPUT_FILE_PATH'"
          }
        ]
      }
    ]
  }
}
```

### Practical Hook Examples

**Example 1: Log every file Claude creates**
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write",
        "hooks": [
          {
            "type": "command",
            "command": "echo \"$(date): Created $CLAUDE_TOOL_INPUT_FILE_PATH\" >> .claude-activity.log"
          }
        ]
      }
    ]
  }
}
```

**Example 2: Prevent Claude from modifying certain files**
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "if echo \"$CLAUDE_TOOL_INPUT_FILE_PATH\" | grep -q 'important-file'; then echo 'BLOCKED: Cannot modify important-file' >&2; exit 1; fi"
          }
        ]
      }
    ]
  }
}
```

### When to Use Hooks

| Good use | Not needed |
|----------|-----------|
| Automatic logging of Claude's actions | One-time tasks |
| Safety guardrails (prevent certain actions) | Simple skill execution |
| Notifications when tasks complete | Tasks you always watch |
| Format validation on outputs | Manual review process |

### For Non-Engineers: Start Simple

Hooks can get technical. Start with just one:

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "echo '✓ Claude finished a task' >> ~/claude-log.txt"
          }
        ]
      }
    ]
  }
}
```

This logs every time Claude finishes a task. Simple, useful, and a good starting point.

## EXECUTE

Let's set up a simple hook:

1. Ask Claude:
```
Create a .claude/settings.json file with a hook that logs
every file Claude creates to a file called .claude-activity.log.
The log should include the timestamp and file path.
```

2. Test it:
   - Ask Claude to create a test file
   - Check `.claude-activity.log` — does it show the entry?

3. If you want, try a more advanced hook:
   - A hook that prevents modification of specific files
   - A hook that sends a notification when a skill finishes

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "What is a Hook in Claude Code?",
    "header": "Hooks Quiz",
    "options": [
      {"label": "A way to connect Claude to external tools", "description": ""},
      {"label": "A command that runs automatically when Claude performs certain actions", "description": ""},
      {"label": "A type of skill that runs on a schedule", "description": ""},
      {"label": "A keyboard shortcut for Claude Code", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "A command that runs automatically when Claude performs certain actions"

If correct: "Right! Hooks are automatic reactions. When Claude creates a file, edits code, or finishes a task, hooks fire automatically. They're great for logging, safety guardrails, and notifications."
If incorrect: "A hook is an automatic reaction — a command that runs by itself when Claude does something. For example: 'whenever Claude creates a file, log it.' You set it up once, and it works every time without you having to remember."
