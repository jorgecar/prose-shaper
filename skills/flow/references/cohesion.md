# Cohesion & Coherence Reference

Cohesion is how consecutive sentences connect; coherence is how a whole passage or document holds together. Load this file when the SKILL.md steps on connection, topic strings, and opening segments need more than the table provides.

---

## Part 1 — Sentence cohesion: old before new

**Principle:** Open each sentence with information the reader already has — a word or idea from the sentence before, or knowledge they bring to the topic — and end on the new information. A column of individually correct sentences only reads as a *passage* when each one hands the next its starting point.

**Example:**
- Wrong: Costs rose 12% this quarter. A delayed vendor contract drove most of the increase.
- Good: Costs rose 12% this quarter. Most of that increase came from a delayed vendor contract.

The Good version opens its second sentence on *that increase* — the idea the first sentence just ended on — and saves the new actor, the vendor contract, for the emphasis position at the end.

Two sub-points:

**(a) The passive is sometimes the right choice — exactly when it keeps the familiar subject at the front.** If the previous sentence ended on *the cache*, prefer the passive `The cache is populated by a nightly job` over the active `A nightly job populates the cache`, which hoists a brand-new actor into first position and breaks the connection. Voice serves cohesion, not the other way around.

**(b) Strip the throat-clearing.** Transitions, attitude markers, and time words piled in front of the subject delay the reader's arrival at the topic. Cut or move them so the familiar idea lands first: `Importantly, in most cases, as of last week, the build was already failing` → `By last week the build was already failing.`

---

## Part 2 — Passage coherence: topic strings

**Principle:** Across a run of sentences, keep the grammatical subjects naming a small, consistent set of characters or ideas. A passage with clean sentences can still feel disorganized when its subjects scatter, because the reader has no fixed topic to track.

**Diagnostic:** Underline the first few words — up to the verb — of every sentence. If they don't form a small, related set, revise so they do.

**Example:**
- Wrong: The cache holds responses for 24 hours. Writes don't trigger invalidation. Stale data is what users see. (subjects: *the cache* / *writes* / *stale data*)
- Good: The cache holds responses for 24 hours, and it never invalidates them on write — so it keeps serving users stale data. (every subject anchored on *the cache*)

Do not vary the subject for variety's sake. Consistency reads as control; rotation reads as drift.

---

## Part 3 — Whole-document coherence

Open each unit — the document, each section, each long paragraph — with a short segment that does two things in order:

1. **Frame the reader's problem** as a *condition* plus *the cost* of leaving it unsolved.
2. **End on the point**, and name the few key themes the body will develop.

Then hold the body to that opening: every sentence must be relevant to the point, and the parts must be ordered deliberately — chronological, coordinate, or logical — rather than left in the order you happened to discover them.

**Example opener:**
> Our deploys take forty minutes, and most of that is the test suite re-running unchanged modules. Releases now ship late while engineers context-switch away waiting. We can cut deploys under ten minutes by caching test results per module.

The first two sentences are the condition and its cost; the last states the point (*cut deploys under ten minutes*) and names the theme the body develops (*caching test results per module*).

---

## Interaction

Old-before-new (this file), the flow step that moves the heaviest word last, and short-to-long sentence shape are the same instinct: lead with what's familiar and simple, close with what's new and heavy. The passive exception here is why `clarity` deliberately keeps some passives instead of flipping every one to active. And `topic-drift` and `buried-lede` (assess) are the diagnoses this file's three parts fix.

---

> **Load-on-demand:** This file is a reference. Load it only when `SKILL.md` guidance on cohesion, topic strings, or opening segments is insufficient for the passage at hand. Do not load it for every flow pass.
