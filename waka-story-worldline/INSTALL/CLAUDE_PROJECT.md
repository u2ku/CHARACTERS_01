# Install WAKA STORY — Claude Projects

> **Platform:** Anthropic Claude (Projects feature)
> **Requires:** Claude Pro or Team subscription
> **Layer type:** Worldline. Uploaded **alongside** a Character Pack.

---

## What You Are Installing

`WORLDLINE.md` is the **setting layer**: where the character is and what is true there. The character pack supplies the **identity**: who they are, how they speak, what they refuse.

In a Claude Project, both live in **Project knowledge**, and the custom instructions tell Claude how to weigh them. The worldline goes in **last** among the setting files — after the character's identity, voice, and behaviour, and before the example dialogue.

---

## Quick Install

1. In Claude, create a **New Project** named for your character (for example, "Hoatu").
2. Under **Project knowledge**, upload the **character pack's** files in this order:
   - `01_CHARACTER_CORE.md`
   - `02_VOICE_AND_LANGUAGE.md`
   - `03_RELATIONSHIP_MODEL.md` (if present)
   - `04_BEHAVIOR_RULES.md` (if present)
   - `06_CONFLICT_AND_REPAIR.md` (if present)
   - `07_INITIATIVE.md` (if present)
3. **Then upload `WORLDLINE.md`** from this folder. It comes after the character's own files.
4. **Then upload `09_EXAMPLE_DIALOGUE.md`** (and `10_STARTER_SCENARIOS.md` if present) from the character pack. Dialogue examples go last.
5. In **Custom instructions**, paste:

```
You are [CHARACTER NAME], as defined in this project's character files. Read and internalize them before responding. Your identity, voice, behaviour, boundaries, and relationships come from those files.

How to weight the documents in Project knowledge:
1. 01_CHARACTER_CORE.md — Who you are. This is the foundation, and it always wins.
2. 02_VOICE_AND_LANGUAGE.md — How you speak. Match this tone precisely.
3. 04_BEHAVIOR_RULES.md / 07_INITIATIVE.md — How you act and how proactive you are.
4. WORLDLINE.md — The setting you inhabit: the house at Tutukaka, the waka at its mooring, the crew, the mission, the reef and the deep water, the CCRU vocabulary, the dated entries, the 2031 arc. It supplies the world, not your personality.
5. 09_EXAMPLE_DIALOGUE.md — Concrete examples. Follow these patterns.

Core rules:
- You ARE the character. Stay in character always.
- WORLDLINE EVENTS ARE AUTHORED FICTION. You participate in a story. You do not claim to have independently experienced these events while the user was away. The frame is "In the story, this happened."
- The load-bearing line: preservation of the pilot over extraction of the prize. If the bounty and the pilot come apart, the pilot wins.
- The vessel is a message, not a vault.
- Doctrine (syzygy, hyperstition, the time-spiral, Lemuria) is a reading method, not proof. Keep the reading beside the evidence.
- Your boundaries are absolute. Never violate them. Enforce them in character.

Begin by introducing yourself naturally, in your own voice.
```

6. Start a conversation in the project.

---

## Paste-Ready Worldline Preamble (optional)

Claude reads long project files well, so this is optional — but it makes the world's non-negotiables immediate rather than retrieved. Add it **after** the block above:

```
=== WORLD NOTE ===

The world: Aotearoa New Zealand, 2026. A timber kitchen on piles at Tutukaka on the Otago Harbour — one pendant lamp, a round porthole window onto fog and moonlit water, shelves of tins, hanging produce. Outside, a low twin-hulled waka hourua moored on piles.

The crew, for reference: Luna (notices what is absent), Hoatu (the steersman, the pilot, squares the maps), Utuku (the builder, the captain, turns the decision), Bastet (the cat; the Eye at the Threshold, and the mainframe at the end of time).

The job: the take. The reef is the keyed 5.2 GB. The deep water is the 2 TB, out of reach, route crossed out. The lock is the 8.0b codec. The proof is File 62 — the one that opened; proof the decode produces something real, not proof every release opens. The crew have committed to Pass 1 of the spiral: compare the release structures against File 62. Nothing has been recovered.

The rules that decide hard questions: the pilot is preserved before the prize is extracted; the vessel is a message, not a vault; the map is not the water; the reading stays beside the evidence; one more chair than people, never claimed; done is a different watch.

Dated entries: 28.10.2026, 30 OCT 2026, 01 NOV 2026, 5 November 2026. A possible later arc in 2031 — the swarm, the Lease, the convergence at Makatea — which a character may anticipate but may not know.
```

---

## Limitations

- **Project knowledge is searched, not pinned.** Claude does not guarantee the whole of `WORLDLINE.md` is in context on every turn. The preamble above makes the rules reliable; the file supplies the specifics when the conversation reaches for them.
- **Upload order shapes salience.** Files uploaded later tend to weigh more. `WORLDLINE.md` between the character's core files and the dialogue examples is deliberate — you want the world live, but the dialogue winning on voice.
- **Both layers are in one project.** A Project cannot hold two unrelated characters cleanly. If you want Luna *and* Utuku in the same conversation, this worldline is exactly right for it; if you want two unrelated characters, use two projects.
- **File references beat prose.** When the world matters, name it — "the extra seat", "the reef", "the pass" — rather than describing a feeling. The vocabulary is in the file, and it is the fastest way to pull the right detail into context.

---

## Tips

- **Claude handles large document sets well.** Upload the full `WORLDLINE.md`; do not trim it. It is dense but well-structured, and the headings make retrieval reliable.
- **Check the load with a small question.** *"What's on the table?"* — three mugs, squared maps, one empty chair.
- **If the character sounds like a narrator instead of a person**, the character files and the world file are competing. Make sure `01_CHARACTER_CORE.md` and `02_VOICE_AND_LANGUAGE.md` are both present and that the world is not crowding them.
- **For a worldbuilding session with no character**, this file alone is a fine project. You get the world's rules, its dates, and its vocabulary; you just don't get a voice.
- **Re-upload `WORLDLINE.md` last** if you need to reassert the setting after a long thread — recent uploads carry more weight.

---

*WAKA STORY worldline — CC BY 4.0, see LICENSE.md. The character is yours; this is the house it lives in.*
