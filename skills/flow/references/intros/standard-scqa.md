---
name: standard-scqa
description: Opens the document with Situation → Complication → Question → Answer in that order, so the reader walks from familiar ground into the problem and then into the point. Reach for it when the audience needs context before the point, when the topic is new to them, or when the reader hasn't yet asked the question your document answers. Avoid for executive readers who already know the situation and only want the answer — they will read three paragraphs of setup as throat-clearing. Keywords — SCQA, standard opener, situation-complication, default introduction, problem-then-point.
---

# Standard SCQA

The problem this solves: when the reader doesn't yet share your framing, jumping to the point lands as an assertion without a foothold. Walking them through the situation and the complication first turns the same point into the answer they were already reaching for.

**Pattern shape.**

- **Situation** — one or two sentences naming a state of affairs the reader already accepts as true.
- **Complication** — what changed, broke, or arrived to make the situation a problem.
- **Question** — the question the complication raises in the reader's mind (usually implicit, not literally written).
- **Answer** — your point: the recommendation, finding, or claim the rest of the document defends.

**Example.**

- Wrong (no SCQA): We should migrate the search index to OpenSearch. The current implementation has issues with relevance tuning, write throughput, and operator tooling. Background — we adopted the current system three years ago.
- Good (Standard SCQA): The search index has run on the same engine for three years and serves about forty million queries a week. In the last quarter, write throughput has dropped twice during the holiday spike, and operators have spent four on-call weekends restoring it by hand. We need a search backend that survives traffic spikes without manual intervention. Migrating to OpenSearch is the shortest path there.

The Good version opens on a fact the reader already accepts (the index, three years, forty million queries), introduces the change that broke it (throughput drops, on-call weekends), implies the question (what do we do?), and lands on the answer.

**When it works.** New topics, mixed audiences, written documents the reader reads top to bottom, situations where the point will land harder if the reader feels the cost first.

**When it backfires.** Executive readers who already lived through the situation; status updates where the situation is obvious; anything under a screen long, where setup eats half the document.
