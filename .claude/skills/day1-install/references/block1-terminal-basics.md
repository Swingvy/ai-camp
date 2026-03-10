# Block 1: Terminal Basics

## EXPLAIN

The terminal is just a text-based way to talk to your computer. Instead of clicking icons, you type commands. That's it.

**Why terminal?** Because Claude Code lives here. Once you're comfortable with 6 commands, you'll never feel lost.

### The 6 Commands You Need

| What you want | Command | What it does |
|---------------|---------|-------------|
| "Where am I?" | `pwd` | Shows your current folder path |
| "What's in here?" | `ls` | Lists files and folders |
| "Go into a folder" | `cd folder-name` | Opens/enters a folder |
| "Go back up" | `cd ..` | Goes to the parent folder |
| "Make a folder" | `mkdir my-folder` | Creates a new folder |
| "Clean the screen" | `clear` | Clears all the text |

### How to open the terminal

**Mac:**
- Spotlight (Cmd + Space) → type "Terminal" → Enter
- Or: Applications → Utilities → Terminal

**Windows:**
- Search → "Command Prompt" or "PowerShell" → Enter

### Reading the terminal

```
Jin@MacBook ~ %
```

This is the **prompt**. It shows:
- `Jin` = your username
- `MacBook` = your computer name
- `~` = you're in your home folder
- `%` = ready for your command

You type after the `%` and press Enter.

## EXECUTE

Open your terminal and try these commands in order:

```bash
# 1. Where am I?
pwd

# 2. What's in here?
ls

# 3. Make a camp folder
mkdir claude-camp

# 4. Go into it
cd claude-camp

# 5. Confirm you're there
pwd

# 6. Go back
cd ..

# 7. Clean up
clear
```

Try each one and see what happens. Don't worry — these commands are completely safe. They just look around and create a folder.

## QUIZ

```
AskUserQuestion({
  "questions": [{
    "question": "You're in the 'Documents' folder and want to go back to your home folder. Which command do you use?",
    "header": "Terminal Quiz",
    "options": [
      {"label": "ls", "description": ""},
      {"label": "cd ..", "description": ""},
      {"label": "pwd", "description": ""},
      {"label": "mkdir home", "description": ""}
    ],
    "multiSelect": false
  }]
})
```

Correct answer: `cd ..`

If correct: "Right! `cd ..` goes up one level. If you want to go straight home from anywhere, you can also type `cd ~`."
If incorrect: Explain each option — `ls` lists files, `pwd` shows location, `mkdir` creates a folder. `cd ..` is the one that moves you up.
