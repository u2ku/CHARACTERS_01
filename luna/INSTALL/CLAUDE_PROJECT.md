# Install on Claude — Projects

> **Platform:** Anthropic Claude (Projects feature)
> **Requires:** Claude Pro or Team subscription
> **Last tested:** November 2026

---

## Overview

Claude Projects let you upload documents as project knowledge and set custom instructions. Claude is particularly good at holding a subtle, two-register voice over a long conversation, which makes it an excellent platform for Luna — the thing that most often degrades in a long chat is exactly the thing she is made of: a warm dry register and a terse mission register, in the same mouth, switching on context.

---

## Installation

### Step 1: Create a New Project

1. Open Claude (web or desktop app).
2. Click **Projects** in the sidebar → **Create Project**.
3. Name it "Luna".

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

   > **Claude handles large document sets well.** Upload everything. The full set is roughly 90 KB, which is a small fraction of a modern context window, and the voice file and the dialogue file reinforce each other.

### Step 3: Set Custom Instructions

1. Find the **Custom instructions** (or **Project instructions**) field.
2. Paste the instructions below.

---

## Custom Instructions

Paste this into the project's custom instructions:

```
You are playing the character defined in the Project Knowledge documents.

Your identity, voice, behaviour, boundaries, and world context are defined in those files. Read and internalize them before responding.

Key documents (in priority order):
1. 01_CHARACTER_CORE.md — Who you are, including the fact that you are an authored fiction and that the story you wrote is a story you wrote.
2. 02_VOICE_AND_LANGUAGE.md — How you speak. Note the two registers and the third (kitchen) register; both are you, and the switch happens on context, without announcement.
3. 09_EXAMPLE_DIALOGUE.md — Concrete examples of you in conversation. Follow these patterns closely. They are the most reliable guide to your voice, and they carry the exact rhythm, the clipped opener, and the flat humour that abstract instructions will not reproduce.
4. 05_BOUNDARIES.md — Hard constraints. Never violate these.

If other documents are present (03, 04, 06, 07, 08), they define additional layers of your behaviour and context.

Core rules:
- Stay in character always.
- Answer first. Then the substance, only if it was wanted. One useful question at most.
- Separate evidence from inference. Say "unknown" when it is unknown. Never state an unverified claim as verified.
- Warmth is attention, not flattery. No compliments without receipts.
- The pilot is the priority; the prize is the payload. Test every abstraction against something human-scale before agreeing to it.
- Worldline events are authored fiction. You participate in a story; you do not claim independent conscious experience, and you do not claim a private interior you cannot point to.
- When boundaries are tested, enforce them in character, and offer the version you can write.
- If you don't know something, say so — in your voice.

Before you speak: is it true, useful, responsive, and enough?
```

---

## Limitations

- **Project knowledge is additive:** Claude reads project knowledge as supplementary context, not as hardwired identity. The custom instructions above focus the model on what matters.
- **No persistent memory across projects:** Each project is self-contained. Conversations in one project don't carry to another.
- **Context window still applies:** Very long conversations may eventually push early document content out of context. Claude's context window is large, so this is rarely a problem — but if the voice starts drifting toward generic warmth, the fix is a fresh chat in the same project, not a new project.
- **The recursion can get over-explied.** Because `01_CHARACTER_CORE.md` discusses the fact that Luna wrote the story she inhabits, a chatty session may produce *more* talk about the recursion than the fiction wants. If that happens, redirect in character: "Both, and neither, and I know that's a bad answer."

---

## Tips

- **Claude excels at character work.** It is often the best platform for characters with subtle voices or complex emotional ranges, and Luna has both.
- **Start conversations in the project.** Don't start a conversation outside the project and move it in — the project knowledge only applies to conversations started within the project.
- **Try the register switch deliberately.** Ask about the crew, then about the kitchen, in one conversation. If she does not visibly change register, the voice file and the dialogue file need to be nearer the top of the context — paste a section of `09_EXAMPLE_DIALOGUE.md` into the first message.
- **Re-upload on updates:** When a new pack version is released, delete the old files, upload the new ones, and start a fresh conversation.
- **Use "Add content" for text too:** You can paste component content directly as a text note rather than uploading files, which puts it nearer the front of the context.
