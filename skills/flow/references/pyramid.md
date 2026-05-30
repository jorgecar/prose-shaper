# Pyramid Logic Reference

Document-level structure: how the themes under a point should relate to it, how to order them, and how to summarize them so a heading or topic sentence earns its place. Load this file when the SKILL.md step on mapping the document — and especially its MECE / logical-order / action-noun sub-bullets — needs more than the table provides.

---

## Part 1 — A document carries one governing thought, supported by grouped ideas

The problem this solves: drafts often present supports in the order ideas arrived, not the order the reader needs them. The result is a body the reader can follow sentence by sentence but cannot reassemble into the point.

Every document carries one governing thought at the top. Below it sit a small handful of themes (typically three or four) that together answer the question the governing thought raises in the reader's mind. Each theme is itself a small governing thought for the supports under it, and so on down. The opening segment — already taught in `cohesion.md` Part 3 — is the apex of this pyramid; section topic sentences (or section headings written as complete thoughts) are the second tier.

Two practical consequences. First, every sentence in the body must answer a question raised by the level above it — no orphan paragraphs. Second, if you cannot summarize a group of supports in one sentence, the group has no governing thought yet, and the section is incomplete.

---

## Part 2 — Themes under a point are mutually exclusive and collectively exhaustive

The problem this solves: when themes overlap, the reader hears the same point twice and assumes the writer is padding; when themes leave a gap, the reader spots the missing support and stops trusting the conclusion. Either failure undermines the same point — that the supports cover the claim.

**Definition.** The themes under a point should be *mutually exclusive* (no two themes restate the same idea) and *collectively exhaustive* (the themes together cover everything the point depends on). Shortened: MECE.

**Before/after — repairing overlap.**

- Wrong: We should adopt the new build system because (1) it caches dependencies, (2) it parallelizes test runs, (3) it cuts CI time, (4) it speeds up the pipeline.
- Good: We should adopt the new build system because (1) it caches dependencies, (2) it parallelizes test runs, (3) it produces reproducible artifacts.

Themes 3 and 4 in the Wrong version were the *effect* of themes 1 and 2, not peers — they restated the conclusion as a reason for it. The Good version drops both and adds a genuinely distinct theme (reproducibility) that wasn't covered.

**Before/after — filling a gap.**

- Wrong: The launch is blocked because the API is unstable and the docs are incomplete.
- Good: The launch is blocked because the API is unstable, the docs are incomplete, and no on-call rotation exists for the first week.

The Wrong version listed two product-side blockers and stopped. The operational blocker — no on-call coverage — is a peer of the other two, not a footnote, and the claim ("blocked") was unsupported without it.

This rule also covers the parallel-form aspect already taught in flow step 6: parallel themes deserve parallel grammar. Here the same instinct works at section scale — peer themes deserve peer status in the structure.

---

## Part 3 — Pick time, structural, or comparative order to match the source

The problem this solves: even MECE themes feel random when their sequence is arbitrary. The reader wastes attention re-ordering them silently, and the cumulative argument loses force.

Any valid grouping was created by one of three analytical moves; the resulting themes carry the order of that move.

**Time order.** The themes are steps in a process or stages of a sequence. The grouping summarizes the effect of running the process end-to-end. Use it when the analytical source is a workflow — onboarding, a deploy pipeline, a quarter-by-quarter forecast.

**Structural order.** The themes are parts of a single whole — a system divided into components, a problem space divided into regions, an org divided into teams. The grouping summarizes the whole. Use it when the source is a stable structure rather than a sequence.

**Comparative order (also called degree order).** The themes share a common quality and differ only in how much of it they carry. The grouping summarizes the kind of thing they all are; the strongest case comes first. Use it when the source is a ranking by importance, severity, or strength of evidence.

**Rule of thumb for picking.** If the source is a process, use time. If the source is a system or stable whole, use structural. If the source is ranked qualities, use comparative. If you cannot name the source, the themes are not yet a group — they are a list.

---

## Part 4 — A heading summarizes what the section says, not what it covers

The problem this solves: section headings like `Background`, `Issues`, or `Findings` tell the reader what category of content follows, not what conclusion to draw from it. The reader skims, the writer's argument disappears under the labels.

**The rule.** A section heading or topic sentence must summarize what the section *says*, not name the topic it covers. Replace category labels with complete-thought summaries: subject + verb + the point.

**Before/after — section heading.**

- Wrong: `Background`
- Good: `Two prior migrations failed for the same reason.`

The Wrong version is a category. The Good version is the conclusion the section will defend — the reader who only skims headings still gets the argument.

**Before/after — topic sentence.**

- Wrong: There are several considerations regarding the cache layer.
- Good: The cache layer adds two days of work and removes one source of stale reads.

The Wrong version is a heading wearing a sentence's clothes. The Good version states the point the paragraph develops — the reader who only reads first sentences still gets the case.

This is the structural twin of the `blank-label` smell (see `skills/assess/references/smell-catalog.md`). The smell catches blank headings on a draft; this rule replaces them.

---

## Part 5 — Section-level prose usually wants induction, not deduction

The problem this solves: writers default to deductive chains ("A; A implies B; therefore B") even when their supports are actually parallel peers. The forced chain reads as labored and exposes any single weak link, when an inductive list would have stood up on its own.

**Deduction.** The supports form a chain. Each support comments on the one before it; the final support carries the conclusion. Use deduction when the argument genuinely depends on each link — for example, when a recommendation is *unexpected* and the reader needs to be walked through the reasoning before the conclusion will land. Limit chains to three or four links; longer chains lose the reader.

**Induction.** The supports are a parallel set — a list of reasons, a set of conditions, several pieces of evidence pointing the same way. The conclusion is the summary of what they share. Use induction by default, especially at the top level of the document, because the reader can absorb the point first and then check each support independently.

**Practical heuristic.** Most prose at the section level wants induction. Reach for deduction only when the supports cannot stand alone — when the strength of the case lives in the chain rather than in any one link.

---

## Interaction

Part 1 names the structure `cohesion.md` Part 3 implies. Part 2 (MECE) is the section-scale version of flow step 6 (parallel structure). Part 4 (action-noun summaries) cures the `blank-label` smell; Part 2's gap detection cures `ungrouped-supports`. Part 5 keeps the agent from forcing deductive shape on inductively related ideas.

---

> **Load-on-demand:** This file is a reference. Load it only when SKILL.md guidance on document structure — the MECE, logical-order, or action-noun sub-bullets in step 1 — is insufficient for the draft at hand. Do not load it for every flow pass.
