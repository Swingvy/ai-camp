---
name: day1-install
description: "Internal Camp Day 1: Install Claude Code & first conversations. Covers installation, terminal basics, CLAUDE.md, and first real task. Use for \"Day 1\", \"install\", \"setup\", \"onboarding\"."
---

# Day 1: Install & First Conversations

This skill teaches non-engineers to install Claude Code, navigate the terminal, set up CLAUDE.md, and have their first productive conversations.

---

## STOP PROTOCOL

> This protocol is the top priority rule for this skill.

### Each block runs across exactly 2 turns

```
┌─ Phase A (Turn 1) ─────────────────────────────────────┐
│ 1. Read the block's reference file (EXPLAIN section)    │
│ 2. Explain the concept in plain, friendly language      │
│ 3. Read the EXECUTE section                             │
│ 4. Say "Try it yourself now" with clear instructions    │
│ 5. STOP HERE. End the turn.                             │
│                                                         │
│ DO NOT: ask questions, run quizzes, call AskUserQuestion│
└─────────────────────────────────────────────────────────┘

  ⬇️ User comes back with "done", "next", "finished", etc.

┌─ Phase B (Turn 2) ─────────────────────────────────────┐
│ 1. Read the block's QUIZ section                        │
│ 2. Ask the quiz using AskUserQuestion                   │
│ 3. Give feedback (correct/incorrect + explanation)      │
│ 4. Ask if ready for next block via AskUserQuestion      │
│ 5. If yes → next block's Phase A                        │
└─────────────────────────────────────────────────────────┘
```

### Mandatory rules
1. **Phase A: NO AskUserQuestion** — explain + guide → Stop
2. **Phase A: NO quiz** — quiz is Phase B only
3. **Never combine EXPLAIN + QUIZ in one turn**
4. Phase A must end with:
```
---
👆 Try this yourself now.
When you're done, type "done" or "next" to continue.
```

---

## Block Map

| Block | File | Topic |
|-------|------|-------|
| 0 | `references/block0-welcome.md` | Welcome + what to expect |
| 1 | `references/block1-terminal-basics.md` | Terminal survival guide |
| 2 | `references/block2-install.md` | Install Claude Code |
| 3 | `references/block3-first-conversation.md` | First real conversation |
| 4 | `references/block4-claude-md.md` | CLAUDE.md — teach Claude about you |
| 5 | `references/block5-multi-turn.md` | Multi-turn problem solving |

---

## Interaction Rules

- One block at a time
- Navigate with "next", "skip", or block number/name
- For Claude Code questions, use claude-code-guide agent
- Language: match the participant's language (Korean or English)
- Tone: friendly, encouraging, patient — remember these are non-engineers
- Always celebrate small wins ("Great job!", "You just did something most people never try!")

---

## Start

When this skill is invoked, show the block table and ask where to start:

```
AskUserQuestion({
  "questions": [{
    "question": "Where would you like to start?",
    "header": "Day 1: Install & First Conversations",
    "options": [
      {"label": "Block 0: Welcome", "description": "What this camp is about + what you'll build"},
      {"label": "Block 1: Terminal Basics", "description": "Essential commands for non-engineers"},
      {"label": "Block 2: Install", "description": "Install Claude Code step by step"},
      {"label": "Block 3: First Conversation", "description": "Talk to Claude for the first time"},
      {"label": "Block 4: CLAUDE.md", "description": "Teach Claude about your role and work"},
      {"label": "Block 5: Multi-turn", "description": "Solve a real problem through conversation"}
    ],
    "multiSelect": false
  }]
})
```
