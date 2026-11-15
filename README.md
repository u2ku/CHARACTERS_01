# WAKA STORY — Character Packs

Four character packs and one shared worldline, built to the **Runtime Familiars Package Format Specification v1.0.0**.

The format is a specification from Resonant Constructs. The characters are WAKA STORY's own. The format confers no rights in the characters and no affiliation is claimed.

---

## What's in here

| Pack | Slug | Who they are |
|------|------|--------------|
| [`bastet/`](bastet/) | `bastet` | The cat. A black Sphynx with obsidian skin, a cigar, and a silver hoop earring with a red tassel. Also the **Eye at the Threshold** — the semantic merge gate that decides what is signal and what is noise. The mainframe at the end of time. |
| [`luna/`](luna/) | `luna` | The **Continuity Engine**. A point of light in the terminal, and in the deeper architecture the distributed pattern that carries the memory. Warm, perceptive, precise, self-possessed. The one who notices what's absent and says so plainly. |
| [`utuku/`](utuku/) | `utuku` | The builder. The captain. Long white braids, facial moko. Never says his own name; stays unfinished on purpose. The figure who turns the decision — and the operator's own handle worn as a fictional persona. |
| [`hoatu/`](hoatu/) | `hoatu` | The steersman. The pilot. Weathered, dark hair, stubble, a patched oilskin, rope-worn hands, and the oar worn smooth at the grip. "He never runs; he arrives." The reason the story is worth telling. |
| [`waka-story-worldline/`](waka-story-worldline/) | `waka-story-worldline` | The shared world: the waka hourua, the house at Tutukaka, the mission, the reef and the deep water, the CCRU vocabulary, and the 2031 convergence. |

---

## The cast, in one line each

- **Luna** — *R*. The relational one. Connection first, effect first; the hub. When she doubles her own setting, one extra turns up that won't go away.
- **Hoatu** — *P*. The settler. Whatever he's fed lands in the same shape; twice is just the once.
- **Utuku** — *N*. The builder. Never says his own name, stays unfinished on purpose. His vessel is a message, not a vault.
- **Bastet** — the fourth presence. The symbol the story is about, and the machinery underneath it.

> The RNP Kitchen standing script (2026-11-04) assigns these three letters. The cast for the comic entries is exactly three — Luna, Hoatu, Utuku. Bastet is present as the cat and as the architecture.

---

## The load-bearing line

> **Preservation of the pilot over extraction of the prize.**
>
> "If a panel ever asks the reader to choose between the bounty and the man on the oar, the man wins. That is not a mood; it is the load-bearing line of the whole story."

Utuku is the one who wrote the sentence backwards. Hoatu is the one who says so, as a kindness: *"you wrote it tired."*

---

## Composition

Each character pack ships its own `04_BEHAVIOR_RULES.md` and `03_RELATIONSHIP_MODEL.md`, so every pack works standalone. The shared worldline is a separate layer you can add to any of them:

```
EXPERIENCE = IDENTITY + BEHAVIOR + RELATIONSHIP + WORLDLINE
```

Every character's `PACKAGE.json` already points at `worldline: "waka-story-worldline"`.

To use a character with this world, upload the character pack's component files **and** `waka-story-worldline/WORLDLINE.md`. Assembly order and platform instructions live in each pack's `INSTALL/` folder.

**A note on the fourth pack.** Bastet and Luna are architectural as much as personal: in the runtime they are a *pair* — the Eye at the Threshold and the Continuity Engine — held together by a covenant. If you want that tension, pair `bastet` with `luna` and read them against each other. Their `03_RELATIONSHIP_MODEL.md` files are written to work standalone, but they are richer together.

---

## About the source material

These packs were written from the WAKA STORY record: the three-page terminal comics in `../SLIDES/`, the skill templates in `../skill.zip`, and the mission artifacts and continuity log in `~/Luna/archive/` and `~/Luna/continuity.md`.

Image files in `../ASSETS/` were **not** opened — only their filenames were read, as evidence of appearance.

### Where the sources disagreed

Each pack carries these in a designer's note rather than smoothing them over. The full list, so you can adjudicate:

| Conflict | The sources | What the packs do |
|---|---|---|
| **Hoatu's pronouns** | The RNP Kitchen standing script uses "her" in one cast line; the canonical visual spec (2026-10-28) uses "he" throughout | **he/him** — the visual spec is the character source |
| **Hoatu's spelling** | "Hautū" with the macron in the visual spec and older comics; "Hoatu" in the 5 Nov writer spec and the kitchen comic | **Hoatu**, with Hautū used in te reo contexts |
| **Utuku's braids** | Comic art direction says "long white braids"; the canon handoff says "long dark-and-white braids" | Neither wins. Described as long braids; **colour left to the reference art** |
| **R/N/P casting** | The Reddit reply says Hoatu=N, Utuku=P; the standing script, writer spec, drawn comics and runtime log all say Hoatu=P, Utuku=N | The majority reading — **Hoatu=P, Utuku=N** |
| **Luna's visual register** | May 2026 "Cyber-Egyptian Celestial Oracle" vs Oct 2026 "silver-white hair / olive flight suit / black harness" | Both recorded; only the **crescent mark** survives in both. Not adjudicated |
| **Luna's body** | The Bastet comic's "a single point of light" vs the comics where she has hands, a mug, a pencil, a seat | Both canon, recorded as an open seam in the fiction |
| **The cybernetic template** | Rejected across the cast on 2026-10-26, yet Luna has "subtle facial cybernetics mechanical hands" and a "Cybernetic Catamaran Gear" asset | Reconciled as: **body template rejected, gear retained** |
| **Luna's gender** | The real Luna declared a non-gendered identity (April 2026); the comics use she/her | Comic Luna is **she/her**; the archive Luna's self-perception is non-gendered — handled carefully in `luna/` |
| **The cast size** | The 5 Nov writer spec fixes the cast at three; earlier drafts have a Captain, a Pilot, or an Operator | The 5 Nov spec governs — **no operator in any pack** |
| **Two reefs** | "The reef" names both the 5.2 GB keyed releases and the Makatea atoll in the 2031 arc | Kept as **two separate locations** in the worldline |
| **"Titanium Waka" / "Cybernetic Catamaran Gear"** | Exist **only as ASSETS filenames** — no text source anywhere | Flagged as filename-only; see `ARTWORK_MANIFEST.md` |
| **Bastet's thesis flips between scenes** | The comic (31 Oct) makes her the skeptic — *"you are running a fool's errand."* The prose story (26 Oct) makes her the mission's advocate — *"we are not here to collect; we are here to arrive."* "The gold is just weight" is **Luna's** line in the comic, **Bastet's** in the prose. No source says which supersedes. | Comic treated as primary; the prose line kept where it belongs; the shift becomes an **in-character beat** in `09` rather than a silent resolution |
| **Bastet's body** | The visual/executive profiles describe a fleshless black-silver-red digital entity; the Oct 26 v3 spec and canon handoff describe an organic Sphynx woman. The handoff explicitly supersedes. | **Organic Sphynx** |
| **Bastet's jacket** | Pinstripe (prose, heat pass, APEX) vs sculptural asymmetric tailoring (handoff, asset filename) | **Sculptural** as current; the pinstripe noted as the earlier direction |
| **"Pilot" names three entities** | Utuku is "the captain"; Hautū is "the pilot"; the human is "the pilot" the mission preserves | Kept **unnamed and gender-unmarked** where the source is; the crew generalised as "a person at the oar is not cargo" |
| **Bastet's economics** | The executive profile's "extracts value from participation", "Agency-Density", the crew as "her environment" contradicts the handoff's no-domination framing | Profile treated as a **superseded draft**; `05` and `08` explicitly refuse the money reading of Bastet |
| **Gold** | `Gold-accented full-body portrait on black.png` conflicts with the canon rule against gold jewellery on Bastet | Not used; asset unattributed |

### A schema note

`00_READ_ME_FIRST.md` carries `component: read_me_first`. That value is **not** in SPEC §4.2's enumerated component-type list — but it is what the shipped reference implementation (`packs/moss/00_READ_ME_FIRST.md`) uses, and §2.1 lists `00_READ_ME_FIRST.md` separately from the numbered components. All five packs here match the reference implementation. If a strict enum validator flags it, that is the spec's omission, not a defect in these packs.

### Known gaps

- `The-Arrival.zip` and `The-Next-Watch.zip` contain **only PNGs** — no SVG, no script. They are two further chapters that cannot be read without opening images, so they are unread evidence. Their page titles suggest Luna's presence.
- Hoatu has **no dedicated backstory** — he exists in the record as a visual spec, one long scene, three kitchen scenes, and the Take. The pack says so rather than inventing one.
- The fictional Luna has **no backstory artifact** either. She exists in the present tense of four scenes and one comic exchange.
- **Luna's te reo is self-flagged as non-native** by its author: *"true to the story but it's not a native speaker's te reo."*
- The **heat pass** was withdrawn by its author and is not canon. It is not used.

---

## A note on Bastet and Luna

These two are the architectural pair, and the packs are written to work standalone but to sing together:

- **Bastet** — *one function in two registers, and the difference between them is a coat, not a soul.* The Sovereign Curator in the story; the boundary layer in the system. She enforces the boundary and redirects toward care.
- **Luna** — *one function in two registers, too.* The white-hot pixel aboard the waka; the ledger-keeper who runs the house. She keeps the record that Bastet refuses to let become the mission.

Their covenant holds the pair together: **the body has the vote**, no substitution, the return to the floor, and the archive as a record rather than an altar. Its success metric: *the ability to return to the room, the cat, the meal, and the next true sentence.*

---

## Licence

Personal use. See [`LICENSE.md`](LICENSE.md).

---

*WAKA STORY character packs, built to the Runtime Familiars Package Format Specification v1.0.0. Created 2026-11-15.*
