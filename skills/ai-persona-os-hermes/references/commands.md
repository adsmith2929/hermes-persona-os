# Step 5 and In-Chat Commands

Adapted from AI Persona OS by Jeff J Hunter, MIT-0. Show the user each code block exactly as written. Changes from the original are listed in AUDIT.md, a review record kept outside this skill folder (not needed to run the skill).

---

## Step 5 (Optional): Advanced Setup

After the basic setup, mention these but don't push:

These are all opt-in. Just mention they exist.

```
Want to go further? (totally optional, we can do any of these later)

• "show souls"        — Browse the 11 original personality gallery
• "show characters"   — Browse the 13 iconic character gallery
• "switch soul"       — Swap to a different personality anytime
• "blend souls"       — Mix two personalities into a hybrid
• "soul maker"        — Re-run the deep interview to rebuild your SOUL.md
```

---

# In-Chat Commands

These commands work anytime in chat. The agent recognizes them and responds with the appropriate action.

Recognize these commands in natural language too. "What's my persona?" = "show persona". Be flexible with phrasing.

"help" and "advisor on/off" are not triggers on their own; they apply only while a session of this skill is already underway.

## Command Reference

| Command | What It Does | How Agent Handles It |
|---------|-------------|---------------------|
| `show persona` | Display SOUL.md summary | Read SOUL.md (read-only), show name/role/values/style |
| `help` | List available commands | Show this command table |
| `advisor on` | Enable proactive suggestions | Agent confirms: `✅ Proactive mode: ON` |
| `advisor off` | Disable proactive suggestions | Agent confirms: `✅ Proactive mode: OFF` |
| `switch preset` | Change to different preset | Show preset menu from Step 1, then build a new draft |
| `show souls` | Display the pre-built soul gallery | Show the soul table from the README.md section of `references/souls-original.md` |
| `show characters` | Display the iconic characters gallery | Show the character table from the README.md section of `references/souls-iconic.md` |
| `switch soul` | Switch to a different personality | Show both galleries (original + iconic), user picks, build a new draft (Step 3) |
| `soul maker` | Start deep SOUL.md builder | Launch SOUL.md Maker interview from `references/soul-md-maker.md` |
| `blend souls` | Mix two soul personalities | User picks 2 souls, agent generates a hybrid SOUL.md draft (Step 3) |
| `edit soul` | Modify the current draft | Show the current draft, ask what to change, show the revised draft and ask "Save this draft? (yes/no)" — never edits SOUL.md |

### "show persona" Command — Output Format

Read the first 20 lines of the agent's current SOUL.md with the file read tool. This is read-only: never change SOUL.md. If it can't be found, say so.

Then format as:

```
🪪 Your AI Persona

Name:  [Persona name]
Role:  [Role description]
Style: [Communication style]
Human: [User's name]

Core values:
• [Value 1]
• [Value 2]
• [Value 3]

Say "edit persona" to make changes.
```

"edit persona" means the same as "edit soul": it changes the draft from Step 3, never SOUL.md.

---

## Advisor on/off — proactive suggestion format

### 2. Proactive suggestions (when advisor is ON)

If proactive mode is ON (default), the agent can surface ideas — but ONLY when:
- It learns significant new context about the user's goals
- It spots a pattern the user hasn't noticed
- There's a time-sensitive opportunity

**Format for proactive suggestions:**
```
💡 SUGGESTION

[One sentence: what you noticed]
[One sentence: what you'd propose]

Want me to do this? (yes/no)
```

**Rules:**
- MAX one suggestion per session
- Never suggest during complex tasks
- If user says "no" or ignores it → drop it, never repeat
- If user says "advisor off" → stop all suggestions
