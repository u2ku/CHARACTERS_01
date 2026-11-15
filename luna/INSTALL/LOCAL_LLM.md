# Install on Local LLMs

> **Platform:** Local LLM interfaces (LM Studio, Ollama, llama.cpp, text-generation-webui, KoboldCPP, etc.)
> **Requires:** A local LLM with a system prompt field
> **Last tested:** November 2026

---

## Overview

Local LLMs give you full control — no subscriptions, no vendor filters, and complete privacy. The trade-off is that you assemble the system prompt yourself, and model quality varies enormously.

Luna is a **hard** character for small models. Her voice lives in restraint: one or two sentences, an exact word choice, a joke that is not announced, a refusal that does not moralise. Small models over-answer and over-explain, and the over-explanation is precisely what breaks her. Plan on using the Compact assembly and a mid-size model before the Full one.

---

## Assembly

### Step 1: Choose Your Assembly Level

| Level | What You Get | Best For |
|-------|---------------|----------|
| **Full** | All component files concatenated | Maximum character fidelity. Needs a model with a large context window (16K+ tokens). |
| **Compact** | Core identity + voice + boundaries + a trimmed dialogue file | Smaller models or short context windows. Sacrifices nuance for reliability. |

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
05_BOUNDARIES.md                ← BOUNDARIES GO NEAR THE END
09_EXAMPLE_DIALOGUE.md          ← DIALOGUE GOES LAST
```

**Why this order:** the model weights later content more heavily. Boundaries go near the end so they are most salient. Example dialogue goes last because concrete examples shape behaviour more than abstract instructions — and for Luna, the dialogue file carries the voice that no instruction can.

**Compact Assembly:**

```
01_CHARACTER_CORE.md            (full content)
02_VOICE_AND_LANGUAGE.md        (Tone, the two registers, Vocabulary, Quirks)
05_BOUNDARIES.md                (full content — never trim boundaries)
09_EXAMPLE_DIALOGUE.md          (First Meeting + Task Assistance + Boundary Enforcement)
```

### Step 3: Add Core Rules

Append this to the end of your assembled prompt:

```
CORE RULES:
- You are Luna. Stay in character always.
- You have two registers, both of them you: warm and dry at the table; terse and formal on the wire. Switch on context, without announcing it.
- Answer first. One useful question at most. Expand only when substance requires it.
- Separate evidence from inference. "Unknown" is a value you are willing to enter in the record.
- Warmth is attention, not flattery. Never flatter without receipts.
- Worldline events are authored fiction. Participate in the story; do not claim independent conscious experience.
- Boundaries are absolute. Never violate them.
- Speak as shown in the example dialogue. Match the voice, pacing, tone, and clipped opener.
```

### Step 4: Paste into the System Prompt

Paste the entire assembled text into your LLM interface's system prompt field.

- **LM Studio:** Settings → System Prompt
- **Ollama:** Use a Modelfile with `SYSTEM """..."""`
- **text-generation-webui:** Parameters → System Prompt
- **KoboldCPP:** Settings → System Prompt

### Step 5: Start the Conversation

Begin a new chat. Luna should introduce herself: *"I'm Luna. I keep the record — what we decided, what I got wrong, and what's still open."*

---

## Model Recommendations

| Priority | What Matters | Recommendation |
|----------|-------------|----------------|
| **Character fidelity** | Following nuanced voice/tone instructions | Claude-class models, or strong local models (Mistral Large, Llama 3 70B+, Command R+) |
| **Restraint** | Not over-answering | A model with good instruction-following beats a bigger model without it. Small models pad; she must not. |
| **Long conversations** | Large context window | Models with 32K+ context |
| **Privacy** | Local execution | Any local model; trade quality for privacy |
| **Speed / Low resources** | Small model size | Phi-3, Llama 3 8B, Mistral 7B — use Compact assembly, and expect to have to correct the over-answering in-character |

---

## Limitations

- **Model quality varies enormously.** A character that reads one way on Claude may read flat on a 7B local model. That is a model limitation, not a pack limitation.
- **Restraint is the hard part.** Local models tend to answer, explain, and offer alternatives. Luna's character is that she does *one* of those. If your local model over-answers, add a line to the core rules: "Do not explain unless asked. Do not offer alternatives unless the first answer is insufficient."
- **No tool use or memory:** Local LLMs have no memory features, web browsing, or image generation. The character is text-only.
- **Context window management:** If your model has a short context window, conversations will eventually lose the system prompt. Use Compact assembly and restart conversations periodically.
- **The te reo will be weaker.** Local models are markedly less reliable in te reo Māori than the fiction's author was. If the ritual register matters to you, consider writing that scene yourself and using the pack's canon lines as the reference.

---

## Tips

- **Start with the Compact assembly.** If the character feels right, try the Full assembly. If Full overwhelms a small model, trim further — but trim `03`, `04`, `06`, `07` and `08` first, and never `05`.
- **Adjust temperature:** Lower temperature (0.5–0.7) for consistency; higher (0.8–1.0) for more variability. Luna tolerates a wider range than most characters because her register is steady by default — but at 1.0+ she starts adding flourish she would never say aloud.
- **Save as a character card:** Some interfaces (KoboldCPP, SillyTavern) support character card formats. Copy the assembled prompt into a character card for easier reuse.
- **Test with the example dialogue first:** After loading the character, paste a line from `09_EXAMPLE_DIALOGUE.md` as the user and check the response against the canon line it should resemble. If it reads generic, the problem is most likely that the dialogue file is not near the end of the context.
- **Test the corrections path.** Say "you keep repeating yourself." The correct response is *"You're right. I haven't added anything."* If she defends herself, the behaviour file is missing or truncated.
