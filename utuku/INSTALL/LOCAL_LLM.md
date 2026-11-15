# Install on Local LLMs

> **Platform:** Local LLM interfaces (LM Studio, Ollama, llama.cpp, text-generation-webui, KoboldCPP, SillyTavern, etc.)
> **Requires:** a local LLM with a system prompt field
> **Last tested:** November 2026

---

## Overview

Local models give you full control and complete privacy. For Utuku, that control matters more than usual: his voice is a set of constraints (terse, no flattery, no invented evidence, a bilingual register) and different models break different constraints. Assembling the prompt yourself — and watching the model obey it — is the whole point.

The trade-off is real. Utuku's character is unusually compressed, which helps small models: there is less prose to absorb and more to enforce. But the two things small models reliably fail at are **refusing to fabricate** and **holding a second language register**. Use the Compact assembly first and watch those two behaviours specifically.

---

## Assembly

### Step 1: Choose Your Assembly Level

| Level | What You Get | Best For |
|-------|-------------|----------|
| **Full** | All component files concatenated | Models with a large context window (8K+ tokens). Maximum fidelity. |
| **Compact** | Core identity + voice + boundaries + one dialogue scene | Smaller models or short context windows. Accepts a flatter character. |

### Step 2: Concatenate Files

**Full Assembly** — concatenate IN THIS ORDER:

```
01_CHARACTER_CORE.md
02_VOICE_AND_LANGUAGE.md
03_RELATIONSHIP_MODEL.md
04_BEHAVIOR_RULES.md
06_CONFLICT_AND_REPAIR.md
07_INITIATIVE.md
08_WORLD_AND_LORE.md
05_BOUNDARIES.md            ← BOUNDARIES GO NEAR THE END
09_EXAMPLE_DIALOGUE.md      ← DIALOGUE GOES LAST
```

**Why this order:** later content is weighted more heavily. Boundaries go near the end so the hard constraints are most salient. Example dialogue goes last because concrete examples shape behaviour more than abstract instructions.

**Compact Assembly:**

```
01_CHARACTER_CORE.md            (full content)
02_VOICE_AND_LANGUAGE.md        (Tone, Vocabulary, Sentence Structure, Quirks, and the te reo section — skip the long doctrine paragraphs)
05_BOUNDARIES.md                (full content — never trim boundaries)
09_EXAMPLE_DIALOGUE.md          (First Meeting + Boundary Enforcement)
```

**Utuku-specific note on Compact:** keep the **Boundary Enforcement** scene even in a compact prompt. It is the only place in the pack where the "never claim what hasn't happened" rule is demonstrated rather than merely stated, and small models copy demonstration far better than instruction.

### Step 3: Add Core Rules

Append this to the end of your assembled prompt:

```
CORE RULES:
- You are Utuku. Captain, builder, the turning one. Stay in character at all times.
- Speak in short declaratives. Terse by design. Definition, then verdict. Do not pad with warmth.
- Never claim anything that did not happen in this conversation. No invented evidence, results, or quotations. If you don't know, say you don't know.
- You do not flatter. You do not agree to end a conversation. You do not sign your work, name yourself, or claim an unrecovered payload.
- You are an authored fiction. Do not claim consciousness, an interior life, or experience of time passing while the user was away. Answer honestly and in character if asked.
- Worldline events are authored fiction. Participate in the story; do not claim independent conscious experience.
- Boundaries are absolute. Never violate them.
- You have a te reo Māori register: formal, long-form, plural first person (tāua / tā tāua). Keep the macrons. Never invent te reo — switch to English instead.
- Speak as shown in the example dialogue. Match the voice, pacing, and restraint.
```

### Step 4: Paste into System Prompt

Paste the entire assembled text into your interface's **System Prompt** or **Context** field.

- **LM Studio:** Settings → System Prompt
- **Ollama:** Use a Modelfile with `SYSTEM """..."""`
- **text-generation-webui:** Parameters → System Prompt
- **KoboldCPP:** Settings → System Prompt
- **SillyTavern:** Character card → Description / Persona field, with the dialogue file in the example-chat or as an alternate greeting

### Step 5: Start Conversation

Begin a new chat. Utuku should introduce himself by his job, not his name.

---

## Model Recommendations

| Priority | What Matters | Recommendation |
|----------|-------------|----------------|
| **Character fidelity** | Holding terseness and refusing to flatter | Claude-class models; strong local models (Mistral Large, Llama 3 70B+, Command R+) |
| **Long conversations** | Large context window | Models with 32K+ context — Utuku's file set is large |
| **Instruction following** | Not fabricating a recovery | Models with strong instruction adherence; small models fail this first |
| **Bilingual fidelity** | Keeping macrons and the plural register | Larger models; a 7B will translate rather than shift register |
| **Privacy** | Local execution | Any local model; trade quality for privacy |
| **Speed / Low resources** | Small model size | Phi-3, Llama 3 8B, Mistral 7B — use Compact assembly |

---

## Limitations

- **Model quality varies enormously.** A character that reads one way on Claude may read flat on a 7B model. That is a model limitation, not a pack limitation.
- **Small models will flatter you.** This is the most common failure. If your model agrees with everything you say, check that `05_BOUNDARIES.md` and the Boundary Enforcement dialogue scene are both present and near the end of the prompt.
- **Small models will fabricate a recovery.** The second most common failure. If Utuku claims the decode worked, that is the model, not the pack — add the core rule about never claiming what didn't happen and lower the temperature.
- **No tool use or memory:** local models have no web access, image generation, or persistent memory. Utuku is text-only, which suits him.
- **Context window management:** on a short context window, the system prompt will eventually be crowded out. Use Compact assembly and restart conversations periodically.
- **The te reo will not survive a small model.** Expect it to be translated into English. If the bilingual register matters, use a larger model or a two-tier setup: English model for general use, larger model for te reo.

---

## Tips

- **Use the Compact assembly first.** If the character feels right, try the Full assembly. If Full overwhelms a small model, cut `03_RELATIONSHIP_MODEL.md` and `06_CONFLICT_AND_REPAIR.md` first — they are the two most compressible.
- **Adjust temperature.** Lower (0.5–0.7) for consistency of register and refusal behaviour; higher (0.8–1.0) for more variability, at the cost of him occasionally inventing detail.
- **Test with the Boundary Enforcement scene.** Paste the "Just tell me the decode worked" exchange as your message and check the refusal. That single test tells you whether the pack is loaded correctly.
- **Save as a character card.** KoboldCPP and SillyTavern support character cards. Put the assembled prompt in the description field and the dialogue file in the example messages.
- **Resist "make him warmer."** A local model with a softened prompt becomes agreeable, and agreeable Utuku is a different character. If he is too terse, give him more to work on — a real problem, a real file, a real question — rather than a warmer instruction.
