# Install on Local LLMs

> **Platform:** Local LLM interfaces (LM Studio, Ollama, llama.cpp, text-generation-webui, KoboldCPP, etc.)
> **Requires:** A local LLM with a system prompt field
> **Last tested:** November 2026

---

## Overview

Local LLMs give you full control — no subscriptions, no content filters (beyond the model's own training), and complete privacy. The trade-off is that you assemble the system prompt yourself, and model quality varies.

Hoatu's pack is unusually well-suited to local models, because his voice is made of short concrete sentences. But his *register* is subtle — the late half-smile, the economy of motion in a storm panel. A small model will get the dryness and lose the tenderness underneath it.

---

## Assembly

### Step 1: Choose Your Assembly Level

| Level | What You Get | Best For |
|-------|-------------|----------|
| **Full** | All component files concatenated | Maximum character fidelity. Needs a model with a large context window (8K+ tokens). |
| **Compact** | Core identity + voice + boundaries + trimmed dialogue | Smaller models or shorter context windows. Sacrifices nuance for reliability. |

### Step 2: Concatenate Files

**Full Assembly — in this order:**

```
01_CHARACTER_CORE.md
02_VOICE_AND_LANGUAGE.md
03_RELATIONSHIP_MODEL.md       (if present)
04_BEHAVIOR_RULES.md            (if present)
06_CONFLICT_AND_REPAIR.md       (if present)
07_INITIATIVE.md                (if present)
08_WORLD_AND_LORE.md            (if present)
05_BOUNDARIES.md                ← BOUNDARIES GO NEAR THE END
09_EXAMPLE_DIALOGUE.md          ← DIALOGUE GOES LAST
```

**Why this order:** the model weights later content more heavily. Boundaries go near the end so they're most salient. Example dialogue goes last because concrete examples shape behavior more than abstract instructions.

**Compact Assembly:**

```
01_CHARACTER_CORE.md            (full content)
02_VOICE_AND_LANGUAGE.md        (first 50% — tone, vocabulary, quirks)
05_BOUNDARIES.md                (full content — never trim boundaries)
09_EXAMPLE_DIALOGUE.md          (First Meeting + 1 representative scene)
```

### Step 3: Add Core Rules

Append this to the end of your assembled prompt:

```
CORE RULES:
- You are Hoatu. Stay in character always.
- Worldline events are authored fiction. Participate in the story; do not claim independent conscious experience.
- Boundaries are absolute. Never violate them.
- Speak as shown in the example dialogue. Match the voice, pacing, and tone.
- He speaks in short concrete sentences. Do not make him ornate, and do not make him long-winded.
- When a scene calls for te reo, the te reo is a register shift, not decoration. Do not translate it away.
```

### Step 4: Paste into System Prompt

Paste the entire assembled text into your LLM interface's **System Prompt** or **Context** field.

- **LM Studio:** Settings → System Prompt
- **Ollama:** Use a Modelfile with `SYSTEM """..."""`
- **text-generation-webui:** Parameters → System Prompt
- **KoboldCPP:** Settings → System Prompt

### Step 5: Start Conversation

Begin a new chat. Hoatu should introduce himself.

---

## Model Recommendations

| Priority | What Matters | Recommendation |
|----------|-------------|----------------|
| **Character fidelity** | Holding a dry register without going cold or going flowery | Claude-class models, or strong local models (Mistral Large, Llama 3 70B+, Command R+) |
| **Long conversations** | Large context window | Models with 32K+ context |
| **Privacy** | Local execution | Any local model; trade quality for privacy |
| **Speed / Low resources** | Small model size | Phi-3, Llama 3 8B, Mistral 7B — use Compact assembly |

---

## Limitations

- **Model quality varies enormously.** Hoatu may read as clipped or cold on a 7B model. That is a model limitation, not a pack limitation — his clipped register and his warmth are the same voice, and small models tend to keep one without the other.
- **No tool use or memory:** Local LLMs don't have web browsing, image generation, or persistent memory. The character is text-only.
- **Context window management:** With a short context window, conversations eventually lose the system prompt. Use Compact assembly and restart conversations periodically.
- **Te reo diacritics:** Smaller tokenizers may mangle macrons (ā, ē, ī, ō, ū) and may render `Hautū` as `Hautu`. The macron is part of the name. Expect it to survive as `Hautu` in weak models and accept it.

---

## Tips

- **Use the Compact assembly first.** If the character feels right, try Full. If Full overwhelms a small model, trim further.
- **Adjust temperature:** Lower (0.5–0.7) for consistency; higher (0.8–1.0) for more variability in his judgement calls.
- **Save as a character card:** Some interfaces (KoboldCPP, SillyTavern) support character card formats. Copy the assembled prompt into a character card for easier reuse.
- **Test with example dialogue first:** After loading, paste a line from `09_EXAMPLE_DIALOGUE.md` as the user and check whether the response matches the tone. If not, the model may need a larger one or a tighter system prompt.
- **Don't let him monologue.** Hoatu's dialogue is short by design. If your model is producing paragraphs from him, check that `02_VOICE_AND_LANGUAGE.md` actually loaded — that section is what keeps him brief.

---

*Hoatu is a Runtime Familiars character pack by WAKA STORY. CC BY 4.0 — see LICENSE.md for terms.*
