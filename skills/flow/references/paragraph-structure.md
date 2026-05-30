# Paragraph Structure Reference

The shape of a paragraph at the level below pyramid logic and above sentence cohesion: where its issue lives, where its point lives, and how an optional final sentence can shift one without moving the other. Load this file when a paragraph reads as competent at the sentence level yet still loses its reader — usually because the issue and point have been collapsed into the same sentence, or the point has landed where the reader is no longer looking for it.

---

## Part 1 — Issue and point are not the same thing

**Principle:** The *issue* of a paragraph is the territory it covers — the question or condition under discussion. The *point* is the claim the paragraph wants the reader to leave with. The school-essay topic sentence assumes issue and point are the same sentence; in adult prose they almost always are not.

**Why the collapse misleads.** When a writer assumes the opener must carry both, two failure modes follow. Either the opener is overloaded — a sentence that names the territory *and* commits to the claim, which gives the rest of the paragraph nothing to do — or the point gets weakened to fit alongside the issue, and the paragraph never reaches the claim the reader needed.

**Example — issue and point collapsed:**
> The deploy pipeline is too slow and we should cache test results. Builds take forty minutes. Engineers context-switch away. The on-call team has stopped trusting the green check.

The first sentence states issue (*the deploy pipeline is too slow*) and point (*we should cache test results*) at once. The next three sentences support the issue but no longer have anywhere to take the point — it was committed before the evidence arrived.

**Example — issue and point separated:**
> The deploy pipeline takes forty minutes, and most of that is the test suite re-running unchanged modules. Engineers context-switch away while builds finish; the on-call team has stopped trusting the green check. Caching test results per module would cut deploys under ten minutes and restore the signal.

The first two sentences name the issue (slow deploys, with the cost). The last sentence makes the point (the proposed fix and its effect). The reader meets the problem before the recommendation, and the recommendation lands harder for it.

---

## Part 2 — Where the point lands

**Principle:** A reader looking for the point of a paragraph looks in one of two places. Either the point arrives as the last sentence of the issue — the issue ends and the claim it raises is stated immediately — or it arrives as the last sentence of the discussion, after the evidence has been laid out. No third location reads as the point; a claim buried mid-discussion will be missed.

**Pattern A — point at the end of the issue.**
The opener names the territory and commits to the claim; the rest of the paragraph defends it.

> The cache layer is the wrong dependency to add this quarter. It adds two days of work and removes one source of stale reads — but the staleness problem is rare, and the two days come out of the migration sprint we already cannot finish. Postpone it to Q3.

The point (*wrong dependency to add this quarter*) lands at the end of the one-sentence issue. The rest of the paragraph supports it.

**Pattern B — point at the end of the discussion.**
The opener names the territory only; the claim arrives once the evidence has been laid out.

> Three things have changed since the last estimate. The data volume has tripled, the schema has acquired two new join paths, and the team has lost the engineer who built the original index. The migration will not finish in one sprint.

The opener names the territory (*three things have changed*). The claim (*the migration will not finish in one sprint*) lands at the end, after the evidence the reader needs in order to accept it.

**How to choose.** Lead with the point when the claim is uncontroversial or the reader has already accepted the framing — they want the recommendation first and the support after. Hold the point until the end when the claim is unexpected, contested, or depends on evidence the reader has not yet seen. A reader who would push back on the claim if they read it first will accept it readily if they meet the evidence first.

---

## Part 3 — The coda — what the last sentence does when it isn't the point

**Principle:** Some paragraphs end with a sentence that is not the point at all. It reverses, sharpens, qualifies, or comments on what came before. This is the *coda*. When a coda is present, the point sits one sentence earlier — at the end of the discussion — and the coda gets the final emphasis position.

**Example — coda reverses:**
> The new build system caches dependencies, parallelizes test runs, and produces reproducible artifacts. Three teams have already migrated, and CI time has dropped by half across all three. We should adopt it next sprint. The vendor's pricing review lands the week after.

The point is *we should adopt it next sprint*. The final sentence (the pricing-review caveat) does not restate the point — it complicates it. A reader trained to take the last sentence as the conclusion would mistake the caveat for the claim; the coda only works because the point has already been stated, clearly, in the sentence before.

**Example — coda sharpens:**
> The migration is on schedule. All three services are running on the new platform, the rollback paths are tested, and the on-call team has signed off. Three weeks ahead, in fact.

The point is *the migration is on schedule*. The coda (*three weeks ahead, in fact*) gives the point a final twist without restating it.

**When to reach for a coda.** Sparingly. The coda is an emphasis tool, not a default ending. Use it when the paragraph has more to say than the point alone, and that extra beat is a reversal, a qualifier, or a sharpening — not a recap. A coda that merely restates the point in different words is a tax on the reader.

**When to avoid it.** In technical procedure, status updates, and any paragraph whose job is to deliver a single unambiguous claim. A coda introduces a second beat, and a second beat is exactly what those registers cannot afford.

---

## Part 4 — Backward link at paragraph start

**Principle:** The first sentence of a paragraph does the same job the first words of a sentence do — it opens on what the reader already has. At the paragraph level, that means echoing the previous paragraph's emphasis, naming the theme the new paragraph will develop, or both. A paragraph that opens on material the reader has not yet been given makes the reader work backward to find the link.

This is the paragraph-scale version of the old-before-new rule from `cohesion.md` Part 1. There the connection runs sentence-to-sentence; here it runs paragraph-to-paragraph.

**Example — paragraph start drops the link:**
> [...prior paragraph ends on *the migration sprint we already cannot finish*.]
>
> Reproducibility is the third reason. The new build system produces deterministic artifacts...

The reader expected the next paragraph to continue on the migration sprint or its consequences. Instead, the new paragraph opens on *reproducibility* — a topic with no link to what came before.

**Example — paragraph start carries the link:**
> [...prior paragraph ends on *the migration sprint we already cannot finish*.]
>
> The migration is also why reproducibility matters now. The new build system produces deterministic artifacts...

The new paragraph opens on *the migration* — the idea the previous paragraph just ended on — and reaches forward to the new theme (*reproducibility*). The reader never loses the thread.

---

## Interaction

This file sits between `cohesion.md` (sentence-to-sentence connection) and `pyramid.md` (whole-document structure). The issue/point distinction is the paragraph-scale version of `pyramid.md` Part 1's governing-thought-and-supports relation: at document scale the governing thought sits above all themes; at paragraph scale the point sits at the end of the issue or the end of the discussion. The coda has no analogue in `pyramid.md` because document structure does not tolerate it — a coda at the document level would read as the conclusion, and a reader who treats it that way will misread the whole. Part 4 (backward link) hands off to `cohesion.md` Part 3, which covers the sentence-level work of carrying the link.

This file fixes two assess smells without naming them directly: paragraphs whose opening sentence promises a claim it never returns to, and paragraphs whose claim arrives somewhere other than the end of the issue or the end of the discussion.

---

> **Load-on-demand:** This file is a reference. Load it only when the SKILL.md step on mapping the document — and specifically when a paragraph's issue and point look collapsed, or its point looks misplaced — needs more than the table provides. Do not load it for every flow pass.
