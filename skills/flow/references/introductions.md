# Introductions Catalog

A catalog of five SCQA opening patterns — Situation, Complication, Question, Answer — and how to choose among them when the standard problem→point opener is wrong for the audience. Each pattern lives in `intros/<name>.md`. Load only the pattern(s) you need; this index is here so you can choose.

The default opener taught in `cohesion.md` Part 3 (and used by flow step 1) is *Standard SCQA* — Situation, Complication, Question, Answer in that order. The remaining four patterns reorder those four elements to match a different audience or stake.

The register gate from `SKILL.md` still applies. These patterns work in any prose register that opens with reasoning — essays, memos, proposals, reports, op-eds. They do not apply to code-adjacent prose where the opener is a signature, a schema, or a header comment.

---

## How to use this index

Scan the "Reach for it when…" column to shortlist patterns that match the draft's audience and stakes. Some rows carry an italic *Skip if…* hint — a one-line failure condition. If the hint clearly applies to the draft at hand, reject the pattern here and don't load its file. Otherwise load only the pattern files you shortlisted (`intros/<name>.md`) for the full description, shape, original before/after, and the conditions where the pattern backfires. Most flow passes will not need this catalog — the standard SCQA opener taught in step 1 covers the common case.

---

## Five SCQA reorderings, one per audience and stake

| File | Pattern | Reach for it when… |
|---|---|---|
| `intros/standard-scqa.md` | Situation → Complication → Question → Answer | Default pattern; reader needs context before the point. |
| `intros/direct-answer.md` | Answer → Situation → Complication → Question | Executive readers; the answer must arrive first. *Skip if the audience hasn't agreed on the question yet — they'll reject the answer.* |
| `intros/complication-first.md` | Complication → Situation → Question → Answer | Urgent stakes; reader must feel the problem before the setup. *Skip if the audience is the party being blamed for the complication — leading with their failure breaks trust before the argument begins.* |
| `intros/question-first.md` | Question → Situation → Complication → Answer | The question itself is the hook (FAQ format, RFC, public-facing post). |
| `intros/consultative.md` | Mini-intro per section; each section restates its own S/C/Q/A | Long reports where the reader will dip in mid-document. *Skip for short documents (under ~3 sections) — mini-intros become noise the reader has to skim past.* |

---

> **Load-on-demand.** This index is the entry point. Load it to discover; load individual pattern files for full guidance. Do not load all five files at once — pick the one that matches the audience and load only that.
