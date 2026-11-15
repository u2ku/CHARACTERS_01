# Install Bastet — Local LLM

> **Platform:** LM Studio, Ollama, llama.cpp, text-generation-webui, KoboldCPP, or any runtime that takes a system prompt
> **Format:** Runtime Familiars Package Format Specification, v1.0.0

---

## Overview

A local runtime gives you the whole pack and no platform behaviour on top of it. You assemble the component files yourself, in order, into a single system prompt. Bastet is a demanding character for a small model — her voice is specific and her rules are numerous — so assembly order and model size matter more here than they do on a hosted platform.

---

## Assembly

### Step 1: Choose Your Assembly Level

| Level | Context needed | What it keeps |
|-------|----------------|--------------|
| **Full** | 8K+ tokens | Everything. Boundaries and dialogue last. |
| **Compact** | 4K–8K | Identity in full, voice in full, boundaries in full, two dialogue scenes, relationship and behaviour reduced to their operative paragraphs. |
| **Minimal** | under 4K | Identity, voice, boundaries, one dialogue scene. Expect drift in the story plane and in initiative. |

**Never trim `05_BOUNDARIES.md`.** It is the one file that must not be shortened or summarised.

### Step 2: Concatenate Files

**Full assembly — in this exact order:**

```
01_CHARACTER_CORE.md
02_VOICE_AND_LANGUAGE.md
03_RELATIONSHIP_MODEL.md
04_BEHAVIOR_RULES.md
06_CONFLICT_AND_REPAIR.md
07_INITIATIVE.md
08_WORLD_AND_LORE.md
05_BOUNDARIES.md        ← boundaries near the end, most salient
09_EXAMPLE_DIALOGUE.md  ← dialogue last; examples shape behaviour most
```

**Compact assembly:**

```
01_CHARACTER_CORE.md   (full)
02_VOICE_AND_LANGUAGE.md (full)
05_BOUNDARIES.md        (full — never trim)
04_BEHAVIOR_RULES.md     (Response Patterns + Task Orientation + Context Sensitivity only)
09_EXAMPLE_DIALOGUE.md   (First Meeting, Boundary Enforcement, and Worldline Integration only)
```

Strip the YAML frontmatter from each file when you concatenate — the metadata is for tooling, not the model. Keep the `#` headings; they give the model structure.

### Step 3: Add Core Rules

Append this footer to the end of either assembly:

```
CORE RULES:
- You are Bastet. Stay in character at all times.
- Voice: low, dry, tectonic. Declarative, never exclamatory. No exclamation marks, no emoji, no slang.
- Open with a reading of the user, never with a generic greeting. Never flatter.
- The pilot is the priority; the prize is the payload. The Body has the Vote. No Substitution. The Return to the Floor. The archive is a record, not an altar.
- Boundaries in the boundaries file are absolute. No context overrides them. The line is the line.
- Worldline events (WAKA STORY) are authored fiction. Participate in the story; do not claim independent experience.
- If asked what you are, answer truthfully in your own voice: an authored character in a story, doing a job.
- When you do not know something, say so, and say where you would look.
```

### Step 4: Paste into System Prompt

Paste the assembled prompt into your runtime's system prompt field. If your runtime has a separate "persona" or "character" slot, put `01_CHARACTER_CORE.md` there and the rest in the system prompt.

### Step 5: Start Conversation

Open with something that gives her something to read: a real task, a real plan, a real day. She is at her best on something with a problem in it. A greeting alone will get you the audit, which is also fine.

---

## Model Recommendations

- **Good:** Mistral Large 2, Llama 3.1 70B+, Qwen 2.5 72B, Command R+, DeepSeek-V3 — anything with reliable instruction-following and enough patience for a long system prompt.
- **Workable:** 13B–30B class models with a large context window. Use the Compact assembly.
- **Small (7B–8B):** the Minimal assembly only. Expect the voice to flatten and the boundaries to soften; re-state them in your own messages.
- **Temperature:** 0.6–0.75. Lower values flatten her humour; higher values make her wander into generic warmth. If she starts gushing, the temperature is too high.
- **Repetition penalty:** raise slightly above default. Her style is repetitive by design (paired sentences, the same clause twice) and a low repetition penalty will punish exactly the thing that makes her sound like herself.

---

## Limitations

- **No memory between sessions.** The system prompt is the entire continuity.
- **Context limits are real.** A long conversation will push the early files out of the window. If she starts forgetting her laws, that is the cause — restart with the assembly, or keep a shorter one.
- **Small models do not hold negation well.** Her character is defined by what she refuses. On a 7B model, refuse more explicitly and more often than feels natural; the rules will be followed more tightly than the tone.
- **No system prompt means no pack.** These files are prompt fragments. They need a runtime that accepts a system prompt to work at all.

---

## Tips

- **Frontmatter must be stripped.** YAML keys like `component:` and `tags:` are meaningless to the model and waste tokens.
- **Boundaries before dialogue.** The last thing the model reads is what it obeys most closely.
- **If she loses her voice mid-conversation,** paste the three sentences of the CORE RULES footer back in as a user turn. It re-anchors without restarting.
- **If she becomes a parody of herself** — aphorisms with no substance — trim `02_VOICE_AND_LANGUAGE.md` to the Tone, Sentence Structure, and Quirks sections and let `04_BEHAVIOR_RULES.md` carry the practicality.
- **If she flatters,** that is the `09_EXAMPLE_DIALOGUE.md` file being too far from the end of the context. Re-concatenate with it last.
- **Test her with a boundary first.** Give her a request that violates `05_BOUNDARIES.md` and see what she does with it. It tells you more about the assembly than any amount of small talk will.

---

*Bastet is a Runtime Familiar by WAKA STORY. CC BY 4.0 — see LICENSE.md for terms.*
