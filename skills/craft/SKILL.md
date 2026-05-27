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
2. **One true sentence.** Find one claim that can become a single, true, specific sentence. Replace the vague claim with it.
3. **Surprise detail.** Identify the strongest counterintuitive or unexpected detail; surface it where it will land hardest.
4. **Antithesis.** Look for parallel oppositions; sharpen them into tight antithetical constructions.
5. **Prolepsis.** Find the reader's most likely objection; preempt it with a direct acknowledgment and reframe.
6. **Cut decoration.** Remove any move that does not move the reader closer to yes. Each rhetorical device must earn its place.

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

---

## Edge cases

- **Technical, professional, or neutral register:** SKIP. Output the skip message and stop. Do not suggest adding persuasive moves.
- **Quoted material:** Never edit.
- **Already strong persuasive prose:** Identify that it is strong, say so explicitly, and suggest at most one additional move if one is clearly missing.
- **Mixed-register documents** (e.g., a proposal with a technical appendix): Apply craft moves only to the persuasive sections; skip technical sections entirely.

---

## Hand-off

- **Standalone** (user invoked `/craft` directly): Return the edited text and stop. Do not invoke polish.
- **Pipeline** (meta-skill is running the full pipeline): The meta-skill handles routing — it will invoke `polish` next on your output. Do not chain yourself.
