---
name: flow
description: Fixes prose that sounds choppy, flat, or monotonous — even when each sentence is grammatically correct. Use when the user says their writing reads robotic, all the sentences are the same length, ideas don't connect, or the rhythm is off. Varies sentence length, enforces parallel structure, moves the heaviest word to the end of each sentence, and trades bare verdicts for evidence the reader can verify. Trigger on — "make it flow", "feels choppy", "improve the rhythm", "sounds robotic", "sentence variety", "parallel structure", "reads flat", "doesn't connect". For wordiness or hedging, prefer /clarity. For persuasive sharpening, prefer /craft. Keywords — flow, rhythm, choppy, parallel, sentence variety, weight-last, evidence.
---

# Flow

## Why this phase matters

Sentences of identical length numb the reader; parallel structure makes related ideas feel related; the heaviest word belongs at the end. When every sentence leads with a verdict ("This is inefficient"), the writing lectures. Reframe as a setup-and-revelation ("Teams spend three hours per deploy — all of it waiting") and the reader draws the conclusion herself.

---

## Procedure

1. **Map the document.** Before fixing sentences, check the shape of the whole. The first paragraph should give the reader a map — what they're reading, why it matters, what to do. If the lede is buried below context-setting, hoist it. Lead with ownership: the data that's *yours*, not the data you happen to have. (`Here's my analysis of the full bandwidth forecast` → `99.4% is media. CMS owns ~0.6%.`)
2. **Vary sentence lengths.** Read the passage aloud. Uniform length numbs; alternating short and long creates pulse. Break a long sentence or merge short fragments as rhythm demands. **Skip this step for technical register** — technical prose values uniformity over rhythmic variation. Steps 3-7 still apply.
3. **Show through evidence, not verdicts.** Every `X is bad/slow/broken` is a verdict — replace it with the cost, delay, or failure that lets the reader draw the conclusion herself. Same rule for interior labels: `extremely nervous` becomes `my keys rattled like they wanted out`. Act, don't tell.
4. **Find parallel ideas; apply parallel structure.** If three items share a relationship, give them the same grammatical form. Mismatched parallels make the reader re-parse.
5. **Cut across expectation.** When a sentence concedes with `X, but Y`, split it. `People assume writing is talent, but it's mostly patience` → `People think writing is talent. It's patience.` The break does the work the conjunction was hiding.
6. **Move the heaviest word last.** The end of a sentence is the emphasis position. Bury the key noun or verb there, not in the middle.
7. **Replace abstractions with the most specific detail you have.** `a lot` → the number; `recently` → the date; `someone` → the person; `a problem` → the exact failure.

---

## Reference tables

### Rhythm & Emphasis

| Wrong | Good |
|---|---|
| The news came unexpectedly and shocked everyone present. | The news hit. Silence followed. |
| I showed up, grasped what lay before me, and claimed victory. | I came, I saw, I conquered. |
| The launch failed because we ignored the data. | We ignored the data. The launch failed. |
| People assume writing is about talent, but it's mostly patience. | People think writing is talent. It's patience. |
| AI is useful but it erodes our ability to think. | AI makes mankind smarter but each person dumber. |

### Evidence & Concreteness

| Wrong | Good |
|---|---|
| The cafe felt lonely. | Two cups sat on the table. Both were cold. |
| I was extremely nervous. | My keys rattled like they wanted out. |
| He brought snacks. | He brought a half-melted candy bar. |
| The meeting was chaotic. | Three people talked. No one listened. |

For paragraph-level before/after demonstrations, see references/examples.md.

---

## Edge cases

- **Procedural / technical steps:** skip "weight last" — chronological order and imperative form take precedence over emphasis placement.
- **Code blocks and tables:** never apply flow edits inside these elements.
- **Persuasive moves:** do not add rhetorical devices, calls to action, or emotional appeals here — that is phase 4 (`craft`).

---

## Hand-off

- **Standalone** (user invoked `/flow` directly): Return the edited text and stop. Do not invoke other phases. End the response with: **Next:** `/craft` if the register is persuasive; otherwise `/polish`.
- **Pipeline** (meta-skill is running the full pipeline): The meta-skill handles routing — it will invoke `craft` if the register is persuasive, otherwise `polish`. Do not chain yourself.
