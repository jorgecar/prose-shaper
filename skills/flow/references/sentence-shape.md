# Sentence Shape Reference

How to write a long sentence that stays clear. Load this file when a sentence must run long and the SKILL.md step on shaping it needs more than the table provides.

---

## The four signs of shapeless length

A long sentence loses the reader when:

1. Its point isn't near the start.
2. It is slow to reach the main verb.
3. It trails a string of tacked-on subordinate clauses after the verb.
4. It interrupts the subject↔verb or verb↔object link with intervening material.

---

## Fix 1 — Get to the subject and verb fast

Move a long opening clause to the end or split it into its own sentence; shorten a long abstract subject by turning the nominalization back into a verb with a real character as its subject; move an interrupting phrase to the start or end.

**Long subject:**
- Wrong: The team's decision to rewrite the scheduler before measuring the bottleneck wasted a sprint.
- Good: The team wasted a sprint: they rewrote the scheduler before measuring the bottleneck.

**Interruption:**
- Wrong: The migration, because it touched every billing table during peak traffic, failed.
- Good: The migration failed because it touched every billing table during peak traffic.

---

## Fix 2 — Extend the line gracefully, not by clause-piling

When you need length, reach for a modifier rather than stacking one relative clause onto another.

**Resumptive** — pause after a key noun, repeat it, and continue with `that…`:
> We rebuilt the deploy pipeline, a pipeline that now ships in four minutes instead of forty.

**Summative** — end a complete clause with a comma, add a noun that sums it up, and continue:
> Latency dropped below 50ms in every region, a result the team had called impossible a quarter earlier.

**Free** — a comment on the subject opening with an `-ing`, `-ed`, or adjective:
> The new index halved query time, freeing the database to absorb the holiday spike.

**Coordinate, short → long** — put the shorter element first:
> The rewrite cut latency and gave the on-call team its first uninterrupted week in months.

---

## Interaction

This is the sentence-level twin of `flow` step 8. It fixes the `sentence-sprawl` smell (assess). Short-to-long ordering is the same principle as old-before-new (see references/cohesion.md): lead with the familiar and simple, close with the new and heavy.

---

> **Load-on-demand:** This file is a reference. Load it only when a long sentence resists the SKILL.md step on shaping. Do not load it for every flow pass.
