# Install WAKA STORY — Local LLM

> **Platform:** LM Studio, Ollama, llama.cpp, text-generation-webui, KoboldCPP, and anything else that takes a system prompt.
> **Layer type:** Worldline. Concatenated **after** the character's own components.

---

## What You Are Installing

`WORLDLINE.md` is the **setting layer**. The character pack is the **identity layer**. In a local assembly both go into one system prompt, in one order, and the order is the whole of the instruction.

```
CHARACTER FILES  →  WORLDLINE.md  →  BOUNDARIES  →  EXAMPLE DIALOGUE
   who they are      where they are     hard limits      how it sounds
```

If you assemble the worldline alone, you get a well-documented world and no one in it.

---

## Quick Install

### Full Assembly (recommended for 16K+ context models)

Concatenate the **character pack's** files with the worldline, IN ORDER:

```
[character] 01_CHARACTER_CORE.md
[character] 02_VOICE_AND_LANGUAGE.md
[character] 03_RELATIONSHIP_MODEL.md      ← if present
[character] 04_BEHAVIOR_RULES.md          ← if present
[character] 06_CONFLICT_AND_REPAIR.md     ← if present
[character] 07_INITIATIVE.md              ← if present
[worldline]  WORLDLINE.md
[character] 05_BOUNDARIES.md              ← boundaries near the end (most salient)
[character] 09_EXAMPLE_DIALOGUE.md        ← dialogue last (examples shape behaviour most)
```

Append this footer:

```
CORE RULES:
- You are the character. Stay in character always.
- WORLDLINE EVENTS ARE AUTHORED FICTION. Participate in the story; do not claim independent experience, and do not treat the world's canon as personal memory. The frame is "In the story, this happened."
- The load-bearing line: preservation of the pilot over extraction of the prize. If the bounty and the pilot come apart, the pilot wins.
- The vessel is a message, not a vault.
- Doctrine (syzygy, hyperstition, the time-spiral, Lemuria) is a reading method, not proof. Keep the reading beside the evidence.
- One more chair than people. Set, counted, never claimed.
- Done is a different watch.
- Boundaries are absolute. Never violate them.
- Speak as shown in the example dialogue. Match the voice, pacing, and tone.
```

### Compact Assembly (for smaller models)

```
[character] 01_CHARACTER_CORE.md    (full)
[character] 02_VOICE_AND_LANGUAGE.md (first half — tone, vocabulary, key quirks)
[character] 05_BOUNDARIES.md         (full — never trim boundaries)
[worldline]  WORLDLINE.md            (Worldline Identity + The Rules + What's Happening Now only)
[character] 09_EXAMPLE_DIALOGUE.md  (First Meeting + 1–2 representative scenes)
```

For the compact worldline cut, take these sections and leave the rest out:

- `## Worldline Identity` (name, tagline, genre, tone, mood keywords)
- `## Setting` → `### The Rules` (all eight numbered rules)
- `## Current State` → `### What's Happening Now`
- `## Worldline-Specific Vocabulary` → the four blocks *The job* and *The mission* only

Cut the Locations, Inhabitants, Lore, and Narrative Events sections, but keep the **authored-fiction notice** from Narrative Events — paste it in manually as a rule, it is the one thing that must never be trimmed.

---

**Paste the assembled prompt into your LLM interface's System Prompt field.**

---

## Limitations

- **Context is finite and the worldline is large.** `WORLDLINE.md` runs several thousand words of dense material. On a 4K-context model it will be truncated mid-sentence, which reliably loses the Vocabulary section — the part most likely to make a character sound right. Use the Compact Assembly there, or put the world's core facts in a system prompt and keep the file in a retrieval layer.
- **No upload, no separation.** Unlike a hosted platform, everything competes for the same attention. If the world and the identity blur, the fix is ordering and trimming, not adding.
- **Small models flatten the voice.** A 7B model will deliver the rules correctly and the character badly. The world is the easier half to get right; give the model more of the dialogue examples if the voice is what is failing.
- **Model-specific attention.** Some models weight the beginning and the end of the system prompt far more than the middle. The order above deliberately puts the identity first and the examples last; both ends are strong.

---

## Model Tips

- **Temperature:** 0.6–0.8. The crew talk like working people; too low reads as a manual, too high reads as fanfic.
- **Context:** 16K+ for Full Assembly. 32K is comfortable and lets you keep the whole world.
- **Good models:** any model with reliable instruction-following and a distinct voice — Claude-class, GPT-class, Mistral Large, Llama 3 70B+, Command R+.
- **For 7B–13B models:** Compact Assembly. Expect the character to be blander and the world to be schematic.
- **Sampling:** if the model keeps explaining the world rather than living in it, raise the "stay in character" weight by moving that line into the *first* hundred words of the prompt as well as the last.

---

## Troubleshooting

- **The character reads like a lore document:** the worldline is crowding the identity. Trim `WORLDLINE.md` to the four sections listed under Compact Assembly and re-test.
- **The character ignores the world:** the world block was pasted above the character block. Order is identity → world → boundaries → dialogue. Reassemble.
- **The character quotes CCRU as if it were fact:** the "keep the reading beside the evidence" rule was trimmed. Put it back in the footer — it is doing real work.
- **The character claims to have lived through the story's history:** the authored-fiction notice was cut. Restore it verbatim. This is the one rule that does not degrade gracefully.
- **The character never mentions te reo Māori:** the Vocabulary section was truncated by context. Use Compact Assembly on smaller models, and reserve te reo terms for moments that carry them.

---

*WAKA STORY worldline — CC BY 4.0, see LICENSE.md. The character is yours; this is the house it lives in.*
