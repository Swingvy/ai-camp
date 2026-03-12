# Block 2: Install the Claude Desktop App

## EXPLAIN

The Claude Desktop App is the easiest way to use Claude Code. It's a desktop application that gives you the full power of Claude Code without needing to install anything through the terminal.

### What is the Claude Desktop App?

- A desktop application that runs Claude Code
- Works on Mac and Windows
- No terminal setup required — just download, install, and start
- Includes all the features: file reading/writing, MCP connections, skills, and more

### How to Install

| Step | What to do |
|------|-----------|
| 1. Download | Go to **claude.ai/download** and download the installer for your platform |
| 2. Install | Open the downloaded file and follow the installation prompts |
| 3. Launch | Open the Claude Desktop App from your Applications (Mac) or Start Menu (Windows) |
| 4. Sign in | Log in with your Anthropic account — follow the on-screen prompts |

### What You Should See

After signing in, you'll see the Claude Code interface — a text input area where you can type your instructions.

```
╭──────────────────────────────────────╮
│ ✻ Welcome to Claude Code!           │
│                                      │
│   /help for help                     │
│                                      │
╰──────────────────────────────────────╯
```

You're in! This is where you talk to Claude.

### Key Things to Know

- **Type naturally** — just write what you want Claude to do in plain English
- **Permissions** — Claude will ask before reading or writing files
- **Exit** — type `/exit` or press `Ctrl+C` to end a session
- **Help** — type `/help` to see available commands

## EXECUTE

Install the Claude Desktop App:

1. Open your browser and go to **claude.ai/download**
2. Download the installer for your computer (Mac or Windows)
3. Run the installer and follow the prompts
4. Open the Claude Desktop App
5. Sign in with your Anthropic account

**Test it:** Once you're in, type this to Claude:

```
Hello! Can you tell me what folder I'm in and list the files here?
```

Claude should respond with your current directory and its contents.

To exit Claude Code, type `/exit` or press `Ctrl+C`.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "How do you install and start using Claude Code?",
    "header": "Install Quiz",
    "options": [
      {"label": "Run complex terminal commands to compile from source", "description": ""},
      {"label": "Download the Claude Desktop App from claude.ai/download and sign in", "description": ""},
      {"label": "Install a browser extension", "description": ""},
      {"label": "Sign up on a website and use it in the browser only", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: "Download the Claude Desktop App from claude.ai/download and sign in"

If correct: "That's it! Download, install, sign in — and you're ready to go. No terminal commands needed for the installation itself."
If incorrect: "The easiest way is to download the Claude Desktop App from claude.ai/download. Just install it like any other application, sign in, and start talking to Claude. No complex setup required!"
