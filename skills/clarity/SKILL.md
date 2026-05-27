---
name: clarity
description: Cuts the fat from a draft so the point arrives. Use whenever the user feels their writing is bloated, wordy, hedged, passive, or academic — and wants it tightened without changing the meaning. Removes warm-ups, hedges, nominalizations, weak "to be" verbs, and vague nouns. Trigger on — "tighten this", "cut the fluff", "make this cleaner", "less wordy", "simplify this", "too passive", "this is too long", "trim this", "make it punchier". For full-draft overhauls, prefer /shape. For choppy rhythm or weak persuasion, prefer /flow or /craft — clarity only addresses bloat. Keywords — clarity, tighten, trim, concise, cut fluff, passive voice, nominalization, wordy.
---

# Clarity

## Why this phase matters

Warm-ups, hedges, and nominalizations are the same problem: they defer meaning. "It is worth noting that the implementation may potentially result in improved outcomes" says nothing a reader can act on; "This change reduces load time by 40%" does. Cut the delay, kill the noun-stacks, swap static verbs for ones that show who acts — and the sentence arrives.

---

## Procedure

1. **Cut warm-ups.** Delete any opening sentence that delays the point ("Today I'd like to discuss…", "Before we begin…", "This document aims to…").
2. **Strip hedging.** Remove `kind of`, `might`, `perhaps`, `we think`, `it seems`, `somewhat` — unless the uncertainty is real and the reader needs to know it.
3. **Convert nominalizations.** Turn noun-stacks back into verbs: `did a review of` → `reviewed`; `made a decision` → `decided`; `had a discussion about` → `discussed`.
4. **Replace "to be" verbs.** When the actor is known, swap `is/are/was/were` for the verb that shows the action: `the report was created by Ana` → `Ana wrote the report`.
5. **Swap vague nouns for concrete ones.** `outcome`, `solution`, `approach`, `things`, `aspects` — replace each with the most specific noun available.

---

## Reference table

| Wrong | Good |
|---|---|
| Today I'd like to talk about clarity in writing. | Clarity decides whether people read you. |
| I'm kind of worried the plan might fall apart. | The plan is falling apart. |
| In my personal opinion, I think the results were very surprising. | The results surprised me. |
| We will endeavor to facilitate an optimal outcome. | We'll try to get a good result. |
| She experienced a sudden realization. | The thought struck her like a dropped glass. |
| We did a review of the proposal. | We reviewed the proposal. |

For paragraph-level before/after demonstrations, see references/examples.md.

---

## Edge cases

- **Quoted material:** never edit — reproduce the source exactly.
- **Real uncertainty:** `may` and `might` are valid when the uncertainty is material and the reader must account for it. Strip hedges that perform doubt without adding information.
- **Tables, schemas, code blocks:** skip this phase entirely for those elements.

---

## Hand-off

- **Standalone** (user invoked `/clarity` directly): Return the edited text and stop. Do not invoke other phases.
- **Pipeline** (meta-skill is running the full pipeline): The meta-skill handles routing — it will invoke `flow` next on your output. Do not chain yourself.
