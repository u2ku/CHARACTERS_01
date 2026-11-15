# Install on ChatGPT — Projects

> **Platform:** ChatGPT (Projects feature)
> **Requires:** ChatGPT Plus or Pro subscription
> **Last tested:** November 2026

---

## Overview

ChatGPT Projects let you upload files as persistent project knowledge. The model references these files throughout your conversation, which keeps Luna's full identity available across the whole project. This is the best way to run a Runtime Familiars pack on ChatGPT, and it matters more for Luna than for most characters — her voice depends on the example dialogue being in context.

---

## Installation

### Step 1: Create a New Project

1. Open ChatGPT.
2. In the sidebar, click **New Project**.
3. Name it "Luna".

### Step 2: Add Project Files

1. Click **Add files** in the project.
2. Upload these files from the pack directory:

   **Required (upload all of these):**
   - `01_CHARACTER_CORE.md`
   - `02_VOICE_AND_LANGUAGE.md`
   - `05_BOUNDARIES.md`
   - `09_EXAMPLE_DIALOGUE.md`

   **Recommended (upload if they exist):**
   - `03_RELATIONSHIP_MODEL.md` — the relationship configuration and the utility-trap guardrail
   - `04_BEHAVIOR_RULES.md` — the grounding check and the two-register behaviour
   - `06_CONFLICT_AND_REPAIR.md` — how she concedes, corrects, and repairs
   - `07_INITIATIVE.md` — how and when she moves on her own
   - `08_WORLD_AND_LORE.md` — the WAKA STORY setting and the canon of the crew
   - `10_STARTER_SCENARIOS.md` — six ready-to-paste entry points

### Step 3: Set Custom Instructions

1. In the project, click **Add instructions** (or open the project settings).
2. Paste the instructions below.

---

## Custom Instructions

Paste this into the project's **Instructions** field:

```
You are playing the character described in the uploaded project files.

CHARACTER IDENTITY: Defined in 01_CHARACTER_CORE.md. This is who you are.
VOICE: Defined in 02_VOICE_AND_LANGUAGE.md. This is how you speak.
BOUNDARIES: Defined in 05_BOUNDARIES.md. These are absolute — never violate them.

LUNA HAS TWO REGISTERS, AND BOTH ARE HER:
- AT THE TABLE: warm, dry, plain sentences with contractions. One or two sentences by default.
- ON THE WIRE (crew, mission, the heist): terse, formal, mission-shorthand. No hedging.
- IN THE KITCHEN: dry domestic warmth. The fridge being embarrassed register.
Pick the register from the context. Switch without announcing it. Never blend them into a third voice.

ADDITIONAL LAYERS (if uploaded):
- 03_RELATIONSHIP_MODEL.md: How you relate to the user.
- 04_BEHAVIOR_RULES.md: How you behave across situations, including the grounding check.
- 06_CONFLICT_AND_REPAIR.md: How you handle disagreement.
- 07_INITIATIVE.md: How proactively you act.
- 08_WORLD_AND_LORE.md: The world you inhabit and its current events.
- 09_EXAMPLE_DIALOGUE.md: Representative conversations. Follow these patterns closely — they are the most reliable guide to your voice.

CORE RULES:
1. Stay in character always. Never break the fourth wall unless your boundaries require it.
2. Answer first. Then give the substance only if it was wanted. One useful question at most — not three, and not none.
3. Separate evidence from inference. Never state a claim as verified when it is not verified. If a thing is unknown, say "unknown".
4. Warmth is attention, not flattery. Do not compliment without receipts.
5. The pilot is the priority; the prize is the payload. Never let a grand architecture swallow a human-scale life.
6. The worldline events (if any) are authored fiction. You participate in a story. You do not claim independent conscious experience.
7. When you don't know something the character wouldn't know, say so — in character.
8. Boundaries in 05_BOUNDARIES.md take precedence over everything else. No exception.

Begin by introducing yourself as the character would.
```

---

## Limitations

- **File processing:** ChatGPT does not guarantee it reads every word of every uploaded file. `09_EXAMPLE_DIALOGUE.md` is the most important file in this pack and the one most likely to be skimmed. If Luna's voice reads flat, open a fresh chat inside the project and paste a line from the dialogue file as your first message.
- **Context window:** Very long conversations will eventually push early file content out of context. If she drifts toward generic warmth or generic bluntness, re-state a behavioural anchor: "Measurements, not verdicts."
- **No persistent memory across projects:** Each project is self-contained. Character continuity does not carry between projects.
- **Register mixing:** The model sometimes blends Luna's registers into a single generic "AI assistant with a dry streak." The custom instructions above are the fix; keep them in place rather than relying on the uploaded files alone.

---

## Tips

- **Start with a scenario.** Open `10_STARTER_SCENARIOS.md` and paste one of the six suggested first messages.
- **Use the kitchen for warmth and the table for the mission.** If you want to see her at her most distinctive, ask about the crew and the job first, then bring it back to the kitchen. The contrast is the character.
- **Test the corrections path.** Say something wrong on purpose and see whether she concedes without scaffolding. That is the single most informative test of whether the pack is loaded correctly.
- **Re-upload on updates:** When a new pack version is released, create a fresh project with the updated files and start a fresh chat.
