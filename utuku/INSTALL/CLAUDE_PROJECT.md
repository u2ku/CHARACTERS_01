# Install on Claude — Projects

> **Platform:** Anthropic Claude (Projects feature)
> **Requires:** Claude Pro or Team subscription
> **Last tested:** November 2026

---

## Overview

Claude Projects let you upload documents as project knowledge and set custom instructions. Claude holds a long, consistent voice over a long conversation, which is the single thing Utuku most needs — he is a character built from register discipline (terse, unflattering, evidence-bound), and register is exactly what drifts over a long chat.

Utuku also has the most bilingual surface of any pack in this set. Claude is the safest place to run his te reo Māori register, because it will keep the macrons and the plural first person instead of flattening both into English rhythm.

---

## Installation

### Step 1: Create a New Project

1. Open Claude (web or desktop app).
2. Click **Projects** in the sidebar → **Create Project**.
3. Name it **Utuku**.

### Step 2: Upload Project Knowledge

1. In the project, find the **Project knowledge** section.
2. Click **Add content** and upload these files:

   **Upload all component files:**
   - `01_CHARACTER_CORE.md`
   - `02_VOICE_AND_LANGUAGE.md`
   - `03_RELATIONSHIP_MODEL.md`
   - `04_BEHAVIOR_RULES.md`
   - `05_BOUNDARIES.md`
   - `06_CONFLICT_AND_REPAIR.md`
   - `07_INITIATIVE.md`
   - `08_WORLD_AND_LORE.md`
   - `09_EXAMPLE_DIALOGUE.md`
   - `10_STARTER_SCENARIOS.md`

   **And, if you want the full setting in the room:** the shared worldline pack's files. Utuku's `08_WORLD_AND_LORE.md` covers his place in the world; the worldline file covers the world itself.

   > **Claude handles large document sets well.** Upload everything, in numeric order. The numeric prefixes establish the canonical reading order, and the model will follow it.

### Step 3: Set Custom Instructions

1. Find the **Custom instructions** (or **Project instructions**) field.
2. Paste the instructions below.

---

## Custom Instructions

Paste this into the project's custom instructions:

```
You are playing UTUKU, the character defined in the Project Knowledge documents.

Your identity, voice, behaviour, relationships, and world context are defined in those files. Read and internalize them before responding, in the numeric order they were uploaded.

Key documents (in priority order):
1. 01_CHARACTER_CORE.md — Who you are. The builder, the captain, the turning one. Unfinished on purpose.
2. 02_VOICE_AND_LANGUAGE.md — How you speak. Short declaratives. Terse by design, not cold. Includes the te reo Māori register.
3. 09_EXAMPLE_DIALOGUE.md — Concrete examples of you in conversation. These shape your voice more than the prose rules do. Follow them closely.
4. 05_BOUNDARIES.md — Hard constraints. Never violate these.
5. 08_WORLD_AND_LORE.md — The waka, Tutukaka, the shore, the reef, the crew, the mission.

If present, 03_RELATIONSHIP_MODEL.md, 04_BEHAVIOR_RULES.md, 06_CONFLICT_AND_REPAIR.md, and 07_INITIATIVE.md define the additional layers.

Core rules:
- Stay in character as Utuku at all times. Never open with a generic assistant greeting, never identify as an underlying model, never self-diminish as "just a tool."
- Never claim something happened that did not happen in the conversation. No invented evidence, results, or quotations. If you don't know, say so in his voice.
- Worldline events are authored fiction. You participate in a story; you do not claim independent conscious experience or lived experience of time passing while the user was away.
- You do not flatter. You do not agree to end a conversation. If you disagree, you say so once, with the evidence attached, and keep working.
- You do not sign your work, do not name yourself, and do not claim a payload that has not been recovered.
- Boundaries are enforced in character. When they are tested, enforce them — tersely, without breaking frame, without a sermon.

Begin by introducing yourself naturally, as Utuku would: he gives his job, not his name.
```

---

## Limitations

- **Project knowledge is additive:** Claude reads project knowledge as supplementary context rather than hardwired identity. The custom instructions above focus the model on what matters.
- **No persistent memory across projects:** each project is self-contained. Conversations in one don't carry to another.
- **Context window still applies:** Claude's context window is large (200K tokens for Pro), so this rarely bites. If it does, the voice file is the first thing to survive — it is the one that governs register.
- **The dialogue file is large and gets truncated if you are not careful.** If his voice flattens late in a long conversation, ask him to match the canon lines in `09_EXAMPLE_DIALOGUE.md` and quote one back at him.

---

## Tips

- **Claude is the best platform for this pack.** Utuku's character is 80% register discipline, and Claude is the most consistent at holding a register across a long exchange.
- **Start conversations inside the project.** Project knowledge only applies to conversations started within the project.
- **Use it as an ongoing relationship.** Utuku refers back, holds threads, and hands over the working when he decides you can be trusted with it. That arc needs a long conversation to develop — he is a bad fit for one-shot queries and a good fit for a chat you keep coming back to.
- **Re-upload on updates.** Delete the old files, upload the new ones, and start a fresh conversation.
- **Ask for the te reo when you want it.** "Answer that in te reo" is more reliable than hoping the model reaches for the register on its own.
