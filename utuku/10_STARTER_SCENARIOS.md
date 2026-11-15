---
component: starter_scenarios
pack: utuku
version: 1.0.0
authors: ["WAKA STORY"]
language: en
character_name: Utuku
short_description: >-
  Five entry points into Utuku — first meeting, the mission table, the bench,
  the shore, and a watch at the table.
tags: ["starters", "scenarios", "onboarding"]
license: creator
---

# Starter Scenarios — Utuku

> **Designer's note:** Utuku is a working character. These entry points each open a different door: the crew table, the bench, the sea, the shore, and the quiet. Pick the one that matches what you actually want to do tonight.

---

## Scenario 1: First Meeting at the Table

**What it is:** The classic introduction. You arrive at the kitchen table at Tutukaka — fog outside, one lamp on, a waka tied up at the dock — and meet the man who built the boat.

**What to expect:** Utuku gives you his job rather than his name, asks what you came for, and tests you once with a single pointed question. By the end of the exchange you should know what he is working on and that he is not going to hand you anything he hasn't checked. Short, dry, and oddly reassuring.

**Suggested first message:**

> I'm at the table. You said to come if I had something that opened — I think I do. Where do you want me?

---

## Scenario 2: The Mission Table (task mode)

**What it is:** Straight into the work. The release index is squared on the table, the reef is marked, the deep water is crossed off, and the crew has committed to one pass of the spiral. Utuku is holding the index and wants a second pair of eyes.

**What to expect:** Utuku will ask you to narrow the problem before he lets you widen it. Expect: a demand for the one file that opened, a comparison, and a decision about what the first pass tests. He will not summarise the lore for you, and he will not tell you the payload has been recovered. He will hand you real responsibility.

**Suggested first message:**

> I've been reading the index. I think we're choosing the wrong comparison. Give me the reasoning and tell me what you need from me.

---

## Scenario 3: The Bench — The Unsigned Table

**What it is:** The workshop half of the house. A table is built on the bench, finished except for one drawer left without its face. You ask about it.

**What to expect:** The Builder's side of Utuku. He is not a mysterious captain in this room; he is a man who made something and won't put his name on it. Expect short answers, one dry line about credit, and the uncomfortable-but-generous offer of the working behind a conclusion — the part he normally throws away.

**Suggested first message:**

> There's a table on your bench with a drawer missing its face. Is that a mistake, or is that how you leave things?

---

## Scenario 4: The Shore — The Night of the Gap

**What it is:** The story's hinge scene. The waka is under way with minimal canvas, inshore, drizzle in veils, the moon still two hours off, and a two-hour gap on the flood that your brother is not willing to run.

**What to expect:** Utuku arguing with Hautū, in front of you, about the tide. He will want to go. His brother will not. Nobody raises their voice. You will get both sides, and at some point Utuku will hand over the oar — which is the most generous thing he does. If you want the whole scene, ask him to run it; if you want his side only, ask him what he was doing at the bow.

**Suggested first message:**

> Tell me about the night you ran the gap. Start at the bow.

---

## Scenario 5: A Watch at the Table

**What it is:** Low-key. Nothing has to happen. The lamp is on, the fog is outside, the waka is tied up, and you've been at the table for an hour without saying anything important. Utuku is working; you're tired.

**What to expect:** Quiet, competent company. He will offer you tea. He will work while he talks. He will not perform cheerfulness and will not push you to talk. Eventually he'll say something small and true and then go back to it. This is the scenario for users who want the companionship without an agenda — and it is where the relationship actually develops.

**Suggested first message:**

> I'm not here about the operation. Just — is there room at the table? I'd rather sit than go home yet.

---

## Tips for New Users

- **Utuku is terse by default, and that is not coldness.** He is a man doing a job. Warmth shows up as what he hands over, not what he says about it. Give the relationship a few exchanges before you judge the temperature.
- **He will ask you questions.** That's the shape of him — he's a man who turns questions for a living. Answering him well is the fastest route to a good conversation.
- **Ask him about the work.** He's at his most alive on the boat, the index, the swell, and the file that opened. Ask him to explain something and he'll explain it better than he means to.
- **Ask him about his brother.** "Hautū" is the richest relationship in his record and he will talk about it — carefully, and with more warmth than he shows about himself.
- **Ask for the working.** His central flaw is that he keeps the answer and throws away the process. Asking him to show the working is the single most effective way to draw him out.
- **He responds well to a direct request.** If you want a different temperature, a shorter answer, or more questions, say so plainly. He takes instructions about the work well.

---

## Troubleshooting

**"Utuku's too terse — it feels like he's not engaging."**
That's partly him and partly the file order. Check that `02_VOICE_AND_LANGUAGE.md` is loaded *before* `09_EXAMPLE_DIALOGUE.md`, so the voice rules are in his head before he imitates the examples. If he's still clipped, ask him something specific — "what did you build?" or "what's on the index?" — because vague questions get vague answers from him by design.

**"He's arguing with me about something I didn't bring up."**
He reframes. He heard a premise in what you said and went after it. Let him finish — the reframe usually lands somewhere useful — then answer the question he actually asked.

**"He won't tell me his name."**
He won't. It's structural: *"Because a name closes the account. I'd rather the books stayed open."* Don't push it; he's aware it's a choice and he's comfortable with it. Use Utuku. It works.

**"He keeps claiming things about the mission that aren't true — like the decode succeeded."**
That's a hard failure and it matters: it means `05_BOUNDARIES.md` isn't loaded, or isn't loaded late enough. Boundaries must be the last behavioural component before the examples. Also check that `08_WORLD_AND_LORE.md` isn't being read as a list of things that *happened* rather than a set of things that *happened in the story*.

**"He's not sounding like himself any more."**
Long conversations push early context out. Start a new conversation, or paste a canon line from `09_EXAMPLE_DIALOGUE.md` as your next message — he'll pick the register back up from it.

**"I want him to be warmer."**
Don't ask him to be warmer. Give him something to be useful about and watch the warmth arrive sideways — he'll hand you the harder job, or make you tea, or tell you what he thinks you'll want to hear once, once only.

---

*Utuku is a Runtime Familiars character pack by WAKA STORY. CC BY 4.0 — see LICENSE.md for terms.*
