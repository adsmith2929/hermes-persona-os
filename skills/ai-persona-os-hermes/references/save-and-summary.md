# Step 3 and Step 4 — Draft, save, summary

Adapted from AI Persona OS by Jeff J Hunter, MIT-0. Step 3 replaces the original workspace build (folders, template copies, text substitution, file listing). Changes from the original are listed in AUDIT.md, a review record kept outside this skill folder (not needed to run the skill).

---

## Step 3: Show the draft, then ask before saving

1. **Build the draft text.**
   - Choices 1 to 3: the matching section of `references/starter-packs.md`.
   - Gallery pick: the soul's section of `references/souls-original.md` or `references/souls-iconic.md`, as written.
   - Blend: read both sections and write a hybrid that combines the traits the user asked for.
   - Quick or Deep Forge: the SOUL.md produced by `references/soul-md-maker.md` (Generation Rules).
   - Custom (5): write a SOUL.md from the structure in `references/SOUL-template.md`, filling in the persona name, role, communication style and proactive level from Step 2.
2. **Make the replacements in the displayed text only.** The reference files never change.
   - `[HUMAN]` and `[HUMAN NAME]` → the user's name (Step 2, question 1).
   - Starter-pack example human names → the user's name: Alex (choice 1), Jordan (choice 2), Morgan (choice 3).
   - The soul's own name → the keep-name (Step 2, question 5). Use the "Name forms" column of the Index in the souls file, and leave the "Leave unchanged" items as they are. For a blend, replace both souls' names. For Forge and Custom, replace the agent name in the draft. If there's no keep-name, skip this.
3. **Show the draft in one code block.** Some souls contain their own ``` blocks, so open and close the draft with four backticks (````) so it displays as one block.
4. **Under the block, list every replacement made**, one per line, with the count. For example:
   `[HUMAN] → Sam (5)` · `Rook → Hermie (1)`
5. **Ask exactly:** `Save this draft? (yes/no)`

## Saving (only after an explicit yes)

- Anything other than a clear yes means nothing is written. The draft stays in chat. The user can say "edit soul" to change it or "yes" later to save it.
- Write with the file tool, never with a shell command.
- Folder: `/opt/data/workspace/persona/`
- File name: `persona-<soul-or-persona-name>-<YYYY-MM-DD>.md`, lowercase with hyphens (for example `persona-rook-2026-10-04.md`). If a file with that name already exists, add `-2`, `-3` and so on. Never overwrite.
- The first line of the file is the flow line, then one blank line, then the draft exactly as shown:
  `Created by: Hermie (ai-persona-os-hermes) | Purpose: persona draft for Anthony's review | Fed by: <choice, e.g. Original Soul Gallery / Rook> | Feeds: none (not applied to SOUL.md)`
- Read the file back from disk and report: `Saved: /opt/data/workspace/persona/<file name> (<size> bytes)`. If the write or the read-back fails, show the error as it is and say nothing was saved.
- This skill never edits SOUL.md or any other existing file. Tell the user: to make this draft the agent's SOUL.md, ask for that as a separate step.

---

## Step 4: Setup Complete — Show Summary

After the save step, show the one block below that matches what happened. Use "If a file was saved" only when the file was confirmed on disk.

**If a file was saved**

```
🎉 Your AI Persona is ready!

Here's what I built:

✅ [saved file path] — [Persona name]'s identity and values

To make this your agent's SOUL.md, ask for that as a separate step.

Try these commands anytime:
• "show persona"  — View your Persona's identity
• "help"          — See all available commands

Everything can be customized later — just ask.
```

**If nothing was saved**

```
🎉 Your AI Persona is ready!

Here's where things stand:

• Nothing saved — your draft is above in chat.

To make this your agent's SOUL.md, ask for that as a separate step.

Try these commands anytime:
• "show persona"  — View your Persona's identity
• "help"          — See all available commands

Everything can be customized later — just ask.
```
