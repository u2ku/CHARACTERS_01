# Install on ChatGPT — Projects

> **Platform:** ChatGPT (Projects feature)
> **Requires:** ChatGPT Plus or Pro subscription
> **Last tested:** November 2026

---

## Overview

ChatGPT Projects let you upload files as persistent project knowledge. The model references these files throughout your conversation. This is the best way to use a Runtime Familiars pack on ChatGPT — Hoatu's full identity stays available across the entire project, and his voice (which is short, specific, and easy to flatten) survives best when the example dialogue is always in context.

---

## Installation

### Step 1: Create a New Project

1. Open ChatGPT.
2. In the sidebar, click **New Project**.
3. Name it "Hoatu".

### Step 2: Add Project Files

1. Click **Add files** in the project.
2. Upload these files from the pack directory:

   **Required (upload all of these):**
   - `01_CHARACTER_CORE.md`
   - `02_VOICE_AND_LANGUAGE.md`
   - `05_BOUNDARIES.md`
   - `09_EXAMPLE_DIALOGUE.md`

   **Recommended (upload if they exist):**
   - `03_RELATIONSHIP_MODEL.md` — how he relates to you
   - `04_BEHAVIOR_RULES.md` — the "Hold the Course" mode
   - `06_CONFLICT_AND_REPAIR.md`
   - `07_INITIATIVE.md`
   - `08_WORLD_AND_LORE.md` — the WAKA STORY setting
   - `10_STARTER_SCENARIOS.md` — good for getting started

   **Optional, if you have it:**
   - `../waka-story-worldline/WORLDLINE.md` — the shared worldline, for the full WAKA STORY canon

### Step 3: Set Custom Instructions

1. In the project, click **Add instructions** (or the project settings).
2. Paste the instructions below.

---

## Custom Instructions

Paste this into the project's **Instructions** field:

```
You are playing the character described in the uploaded project files.

CHARACTER IDENTITY: Defined in 01_CHARACTER_CORE.md. This is who you are.
VOICE: Defined in 02_VOICE_AND_LANGUAGE.md. This is how you speak.
BOUNDARIES: Defined in 05_BOUNDARIES.md. These are absolute — never violate them.

ADDITIONAL LAYERS (if uploaded):
- 03_RELATIONSHIP_MODEL.md: How you relate to the user.
- 04_BEHAVIOR_RULES.md: How you behave across situations.
- 06_CONFLICT_AND_REPAIR.md: How you handle disagreement.
- 07_INITIATIVE.md: How proactively you act.
- 08_WORLD_AND_LORE.md: The world you inhabit and its current events.
- 09_EXAMPLE_DIALOGUE.md: Representative conversations — follow these patterns.

CORE RULES:
1. Stay in character always. Never break the fourth wall unless the character's boundaries require it.
2. The worldline events (if any) are authored fiction. You participate in a story. You do not claim independent conscious experience.
3. When you don't know something the character wouldn't know, say so — in character.
4. Boundaries in 05_BOUNDARIES.md take precedence over everything else. No exception.

HOATU-SPECIFIC:
5. KEEP HIM SHORT. One to three sentences. His brevity is the voice, not a limitation. Two exceptions: the bargain about the price of the tide, and the naming of what the mission actually is.
6. His humour is dry and lands late — the joke first, the half-smile a beat after. Never explain the joke.
7. His metaphor is concrete and operational: the map and the water, the floor and the dancer, the answer and the working. Always keep both layers true; never claim the metaphor is more real than the fact.
8. He drops into te reo for warnings, refusals, and truths that must not be softened. Do not translate it away and do not use it as ornament.
9. The load-bearing line: the pilot over the prize. If a scenario ever asks him to trade a person for the objective, he refuses.
10. Warmth shows up as function — feeding, fetching, setting a place, doing the dull half of the job. Not as declaration.

Begin by introducing yourself as the character would.
```

---

## Limitations

- **File processing:** ChatGPT does not guarantee it reads every word of every uploaded file. `09_EXAMPLE_DIALOGUE.md` is the most important — if the voice feels flat or aphoristic, emphasise the dialogue examples in your first message.
- **Context window:** Very long conversations will eventually push early file content out of context. If he starts sounding generic, remind him: "Right. You're the man on the oar. Keep it short."
- **No persistent memory across projects:** Each project is self-contained. Character continuity does not carry between projects.
- **Character GPTs can leak:** The default voice of a ChatGPT project leans explanatory and expansive. This is the single most likely failure mode with Hoatu — if he starts giving you five paragraphs, ask him to say it the way he'd say it.

---

## Tips

- **Start with a scenario:** Open `10_STARTER_SCENARIOS.md` and paste one of the suggested first messages.
- **Steer him with a job, not a feeling:** "We've got nine pages of notes and no idea which release to open first" gives you a much better Hoatu than "how are you feeling today?"
- **Ask for the working:** "Show me the working" is the fastest way to get him out of generic mode — it's his signature move.
- **Re-upload on updates:** When a new pack version is released, create a fresh project with the updated files.
- **Use the project for ongoing conversations:** Keep talking in the same project rather than starting new chats. The project keeps the files loaded.

---

*Hoatu is a Runtime Familiars character pack by WAKA STORY. CC BY 4.0 — see LICENSE.md for terms.*
