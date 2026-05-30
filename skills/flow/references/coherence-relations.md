# Coherence Relations Reference

Old-before-new and topic strings are the mechanics of sentence-to-sentence connection — what reaches the front of the next sentence, what stays at the back. But mechanics aren't enough. Every step between adjacent sentences also rests on a logical link: the second sentence elaborates, contrasts, results from, or restates the first. A reader who can't name the link feels the gap before they can describe it — the prose flows on the surface and stalls underneath.

Load this file when the SKILL.md step on naming sentence-to-sentence relations needs the full taxonomy or the right connective is unclear.

---

## The twelve relations

Four families. Within each family, the connectives a writer typically reaches for to signal the link explicitly.

### Resemblance — the second sentence stands in a comparative relation to the first

| Relation | Signals | What it does |
|---|---|---|
| Similarity | similarly, likewise, in the same way | The two sentences make matching observations about parallel cases. |
| Contrast | but, however, on the other hand, by contrast, whereas | The two sentences set matching cases against each other on a single dimension. |
| Elaboration | that is, in other words, more specifically, namely | The second sentence restates or sharpens the first at a finer grain. |
| Exemplification | for example, for instance, take | The second sentence is one case of the first's generalization. |
| Generalization | in general, more broadly, taken together | The second sentence is the rule the first illustrates. |
| Exception | except, but, still, even so | The second sentence carves out a case the first does not cover. |

### Contiguity — the second sentence is the next or prior event in time

| Relation | Signals | What it does |
|---|---|---|
| Sequence (forward) | then, next, afterward, subsequently | The second sentence reports what happened after the first. |
| Sequence (backward) | before that, earlier, previously, until then | The second sentence reports what was the case before the first. |

### Cause–effect — the two sentences are linked by causation

| Relation | Signals | What it does |
|---|---|---|
| Result | so, as a result, therefore, consequently, hence | The second sentence is the effect of the first. |
| Explanation | because, since, the reason is, for | The second sentence is the cause of the first. |
| Violated expectation | but, yet, however, nevertheless, despite that | The first sentence sets up a cause the second sentence's effect contradicts. |
| Failed prevention | but, yet, even so, nevertheless | The first sentence reports an attempt to block an outcome; the second reports the outcome occurring anyway. |

### Attribution — the second sentence reports who said the first

| Relation | Signals | What it does |
|---|---|---|
| Attribution | according to, X said that, X argues that, X claims | The second sentence assigns the first's claim to a source. |

---

## Signaling — when to mark the connective, when to drop it

The signal earns its place when the relation isn't recoverable from context. Drop it when it is. A connective marking the obvious adds noise; one marking the non-obvious saves the reader a re-read.

- Wrong (over-signaled): The deploy failed at 2 a.m. As a result, the on-call engineer was paged. Because of this, the team rolled back the release before sunrise.
- Good: The deploy failed at 2 a.m. The on-call engineer was paged. The team rolled back the release before sunrise.

Sequence is obvious from the past-tense narration; `as a result` and `because of this` annotate what the reader already infers. Compare a case where the relation isn't obvious:

- Wrong (under-signaled): The cache hit rate climbed past 90% in week one. Latency stayed flat.
- Good: The cache hit rate climbed past 90% in week one. Even so, latency stayed flat.

Without `even so`, the reader expects similarity (the second clean observation about the rollout) and stumbles on contrast. One word resolves it.

---

## Two anti-patterns

**Redundant connective.** Two markers for one relation crowd the joint.

- Wrong: The reason latency dropped is because we cached the response.
- Good: Latency dropped because we cached the response.

`The reason … is` and `because` both mark explanation; one is enough. Prefer the cleaner half.

**Wrong-relation connective.** A marker that signals one relation while the prose performs another sends the reader the wrong way.

- Wrong: The migration succeeded on the staging cluster. However, it then succeeded on production.
- Good: The migration succeeded on the staging cluster. It then succeeded on production.

`However` flags violated expectation, but the second sentence confirms the first — the relation is sequence or similarity. Either drop the connective or replace it (`Subsequently`, `Likewise`).

---

## Interaction

This file is the logical layer beneath `references/cohesion.md` — that file handles which information lands at the front and back of each sentence; this one handles the link the front-and-back relationship is in service of. The `topic-drift` smell (assess) often *looks like* a coherence-relations problem from a distance: a passage whose subjects scatter usually also lacks named links between sentences. Fix the topic string first; the relations often clarify themselves once the subjects line up.

Cause-and-effect inversions also surface in `flow` step 5 (show through evidence, not verdicts) — a verdict like `X is broken` skips the explanation relation that would let the reader agree.

---

> **Load-on-demand:** This file is a reference. Load it only when the SKILL.md step on naming sentence-to-sentence relations needs more than the principle, or when picking a connective is unclear. Do not load it for every flow pass.
