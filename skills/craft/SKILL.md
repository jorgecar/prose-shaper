---
name: craft
description: Makes a pitch, proposal, or argument actually land — moving the reader closer to yes. Use only on persuasive writing (pitches, proposals, op-eds, executive summaries, escalations, stakeholder emails) that is already clear and structurally sound. Applies rhetorical moves — one true sentence, a surprise detail, antithesis, prolepsis (preempting the reader's objection). Trigger on — "make this pitch sharper", "this needs to land", "add rhetorical punch", "make this more persuasive", "sharpen the argument", "this doesn't land", "make this compelling", "needs more punch". Do NOT use for technical docs, ADRs, meeting notes, neutral reports, or status updates — persuasive moves applied to the wrong register make writing worse, not better. Keywords — craft, persuasion, rhetoric, pitch, antithesis, prolepsis, compelling, sharpen.
---

# Craft

## Why this phase matters

Persuasion fails when it argues instead of shows. A single true, specific sentence — the one detail too precise to dismiss — does more than a paragraph of claims. Antithesis sharpens the stakes ("Not a rewrite; a replacement"). Prolepsis earns trust by naming the objection before the reader raises it. None of these are decoration; each one moves the reader closer to yes.

---

## Procedure

1. **Register gate.** Check the register block from `assess`. If `register != persuasive`, do not edit. Persuasive moves applied to the wrong register produce worse writing: antithesis in an ADR reads as preening; prolepsis in a meeting note reads as defensive. Output exactly: "Craft skipped — register is <value>, not persuasive." Then stop.
2. **Open at the change.** Start late — enter at the moment of movement, not the windup. Lead with ownership: name the data that's yours, not the data you happen to have. (`It was a normal Tuesday. I made coffee...` → `At 9:17, my manager wrote: "We need to talk."`) The reader meets your point, not your throat-clearing.
3. **One true sentence.** Find one claim that can become a single, true, specific sentence. Replace the vague claim with it.
4. **Surprise detail.** Identify the strongest counterintuitive or unexpected detail; surface it where it will land hardest.
5. **Antithesis.** Look for parallel oppositions; sharpen them into tight antithetical constructions.
6. **Prolepsis.** Find the reader's most likely objection; preempt it with a direct acknowledgment and reframe.
7. **Let dialogue do work.** Where a direct quote or exchange compresses an entire paragraph of summary, use it. `The team disagreed about the feature` → `"Ship it." / "Over my dead laptop."` Two voices, one decision, no narration.
8. **Small paragraphs as stories.** A short paragraph can carry a three-beat micro-story: setup, turn, landing. `Write every day. Most days will be dull. Then one won't.` Short paragraphs pivot harder than long ones.
9. **Reach for a named figure (only if the core moves left a gap).** A sentence may still want a specific shape — a memorable closing, a chain of cause, a pile-up that overwhelms — that none of the six moves above delivers. Consult `references/rhetorical-figures.md`. Shortlist figures by the "Reach for it when…" prompts in the index and load only the file(s) for the figure(s) that fit (each lives under `references/figures/<name>.md`). Most paragraphs need none of these.
10. **Cut decoration.** Remove any move or figure that does not move the reader closer to yes. Each rhetorical device must earn its place.

---

## Reference table

| Principle | Wrong | Good |
|---|---|---|
| One true sentence | The product got way better. | Crashes dropped from daily to once a month. |
| Surprise detail | The meeting was chaotic. | Three people talked. No one listened. Someone ate a yogurt. |
| Antithesis | AI is useful but it can also be harmful. | AI makes mankind smarter but each person dumber. |
| Prolepsis | This will be hard, but worth it. | You'll say this is risky. It is. Doing nothing is riskier. |
| Repeat with intention | They built the sloppy app fast. | They vibed the vibe and slopped the slop. |
| Rewrite for the reader | This paragraph explains the same point three times. | This paragraph makes one point once. |

For deeper guidance on each move, see `references/rhetorical-moves.md`.

Beyond the six moves, `references/rhetorical-figures.md` indexes ~30 named rhetorical figures from Forsyth's *The Elements of Eloquence* (anaphora, chiasmus, anadiplosis, litotes, congeries, and more). Each figure has its own file under `references/figures/` with a `description` in YAML frontmatter, mirroring SKILL.md's format. Read the index to discover; load only the figure file(s) you need. Procedure step 9 covers when to reach for it.

---

## Edge cases

- **Technical, professional, or neutral register:** SKIP. Output the skip message and stop. Do not suggest adding persuasive moves.
- **Quoted material:** Never edit.
- **Already strong persuasive prose:** Identify that it is strong, say so explicitly, and suggest at most one additional move if one is clearly missing.
- **Mixed-register documents** (e.g., a proposal with a technical appendix): Apply craft moves only to the persuasive sections; skip technical sections entirely.

---

## Hand-off

- **File Mode** (invoked on a file on disk): before writing, enter plan mode and show the whole-document before→after diff plus why; write the file only after the user approves. See `../shared/file-mode.md`.
- **Standalone** (user invoked `/craft` directly): Return the edited text and stop. Do not invoke polish. End the response with: **Next:** `/polish` for the final scan.
- **Pipeline** (meta-skill is running the full pipeline): The meta-skill handles routing — it will invoke `polish` next on your output. Do not chain yourself.
