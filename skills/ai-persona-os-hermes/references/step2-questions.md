# Step 2: Gather Context — questions

Adapted from AI Persona OS by Jeff J Hunter, MIT-0. Show the user the matching code block exactly as written. Changes from the original are listed in AUDIT.md, a review record kept outside this skill folder (not needed to run the skill).

## Step 2: Gather Context (ALL presets)

After the user picks a preset, the agent needs a few personalization details. Ask ALL of these in ONE message:

Ask these questions in a single message. Do not split across turns.

For presets 1-3 and SOUL.md Maker gallery picks:
```
Great choice! I need a few details to personalize your setup:

1. What's YOUR name? (so your Persona knows who it's working for)
2. What should I call you? (nickname, first name, etc.)
3. What's your role? (e.g., Founder, Senior Dev, Marketing Director)
4. What's your main goal right now? (one sentence)
5. What name should this persona keep? (for example, the name your agent already has)
```

For preset 5 (custom), ask these ADDITIONAL questions:
```
Let's build your custom Persona! I need a few details:

1. What's YOUR name?
2. What should I call you?
3. What's your role? (e.g., Founder, Senior Dev, Marketing Director)
4. What's your main goal right now? (one sentence)
5. What's your AI Persona's name? (e.g., Atlas, Aria, Max)
6. What role should it serve? (e.g., research assistant, ops manager)
7. Communication style?
   a) Professional & formal
   b) Friendly & warm
   c) Direct & concise
   d) Casual & conversational
8. How proactive should it be?
   a) Reactive only — only responds when asked
   b) Occasionally proactive — suggests when obvious
   c) Highly proactive — actively anticipates needs
```

For preset 4 (SOUL.md Maker) with Quick/Deep Forge: The SOUL.md Maker interview in `references/soul-md-maker.md` gathers its own context. After the interview generates a SOUL.md, come BACK to this step and ask ONLY questions 1-5 above (name, nickname, role, goal, keep-name) for personalizing the draft.

**Defaults for missing answers (notes, not shown to the user):**
- Name → "User"
- Nickname → same as name
- Role → "Professional"
- Goal → "Be more productive and effective"
- Persona name → "Persona" (custom/preset 5 only)
- Persona role → "personal assistant" (custom/preset 5 only)
- Comm style → c (direct & concise)
- Proactive level → b (occasionally proactive)
- Keep-name (question 5) → none: the soul keeps its own name. For preset 5 (custom), question 5 there ("What's your AI Persona's name?") is the persona name, so no extra question is asked.
