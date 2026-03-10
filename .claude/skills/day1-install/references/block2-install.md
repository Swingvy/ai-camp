# Block 2: Install Claude Code

## EXPLAIN

Installing Claude Code takes 2 steps:
1. Install Node.js (the engine Claude Code runs on)
2. Install Claude Code itself

### Step 1: Check if Node.js is installed

```bash
node --version
```

If you see something like `v20.11.0` → you're good, skip to Step 2.
If you see "command not found" → install Node.js first.

**Install Node.js:**

| Platform | Command |
|----------|---------|
| Mac (with Homebrew) | `brew install node` |
| Mac (without Homebrew) | Install Homebrew first: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` then `brew install node` |
| Windows | Download from nodejs.org and run the installer |

### Step 2: Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

### Step 3: Launch it

```bash
cd claude-camp
claude
```

The first time, it will ask you to log in. Follow the browser prompt — you'll authenticate with your Anthropic account or API key.

### What you should see

After login, you'll see something like:

```
╭──────────────────────────────────────╮
│ ✻ Welcome to Claude Code!           │
│                                      │
│   /help for help                     │
│                                      │
╰──────────────────────────────────────╯
```

You're in! This is where you talk to Claude.

## EXECUTE

Run these commands in your terminal:

```bash
# Check Node.js
node --version

# Install Claude Code (if not already installed)
npm install -g @anthropic-ai/claude-code

# Go to your camp folder
cd claude-camp

# Launch Claude Code
claude
```

Follow the login prompt in your browser. Once you see the welcome message, you're done!

**Test it:** Type this to Claude:

```
Hello! Can you tell me what folder I'm in and list the files here?
```

Claude should respond with your current directory and its contents.

To exit Claude Code, type `/exit` or press `Ctrl+C`.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "After installing, what command starts Claude Code?",
    "header": "Install Quiz",
    "options": [
      {"label": "start claude-code", "description": ""},
      {"label": "npm run claude", "description": ""},
      {"label": "claude", "description": ""},
      {"label": "open claude-code", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: `claude`

If correct: "That's it! Just `claude`. Simple as that. And `/exit` or Ctrl+C to leave."
If incorrect: "It's just `claude` — one word. Claude Code keeps things simple."
