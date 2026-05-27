---
name: polish
description: Catches the things that would embarrass the user if they shipped the draft as-is. Use as the last step before sending or publishing — when the writing is already structurally sound and just needs a final pass. Fixes punctuation (Oxford commas, em/en dashes, colons vs semicolons), caps exclamations, strips ellipses, and reads every sentence against one question — does it earn its place? Trigger on — "final pass", "proofread this", "ready to send?", "last check", "clean it up", "one more pass", "almost done", "before I hit send". For rough drafts that still need structural work, prefer /shape or /clarity — polish is rescue too late if the prose is still bloated or choppy. Keywords — polish, proofread, punctuation, Oxford comma, em dash, final pass, ready to send.
---

# Polish

## Why this phase matters

By this pass, the writing should be structurally sound — polish is not rescue, it is final accountability. The Oxford comma removes one class of ambiguity without cost; the em dash signals interruption or amplification; the colon promises what follows delivers on it. Read every sentence as a line item: if it adds no information, shifts no weight, and creates no momentum, it does not earn its place.

---

## Procedure

1. **Punctuation pass.** Apply every rule in the reference table below. For rules not covered here, see `references/punctuation-table.md`.
2. **Exclamation cap.** Allow 1 exclamation mark per document maximum in professional or persuasive writing. Allow 0 in technical writing. Convert extras to periods.
3. **Strip ellipses.** Remove all ellipses unless they signal a genuine omission from a direct quote. Replace trailing ellipses with periods; replace mid-sentence ellipses with a dash or rewrite.
4. **Sentence audit.** Read each sentence: does it add information, shift weight, or create momentum? If none of those three, cut it.
5. **Final read.** One top-to-bottom pass for typos, orphaned words, and anything the previous steps missed.

---

## Punctuation reference (abbreviated)

| Rule | Example |
|---|---|
| Oxford comma | "APIs, webhooks, and events" |
| Comma after introductory phrase | "After the migration, the system stabilized." |
| Em dash for interruption or amplification | "The fix — which took three days — shipped Friday." |
| En dash for ranges | "Pages 1–5" |
| Colon introduces explanation or list | "The root cause was clear: a missing index." |
| Semicolon connects related independent clauses | "The API returns JSON; it doesn't support XML." |

For the full 12-row table covering hyphens, parentheses vs em dashes, ellipses, and all edge cases, see `references/punctuation-table.md`.

---

## Edge cases

- **Quoted material:** Do not edit punctuation inside quoted text.
- **Code blocks and tables:** Never edit. Pass over them without changes.
- **Constrained formats** (Jira summaries, commit messages, tweet-length copy): Brevity overrides most rules. Apply exactly three: Oxford comma in lists, en dash for ranges, em dash for interruption. Skip semicolon/colon enforcement, ellipsis policy, and the sentence audit step.
- **Non-native English prose:** Apply punctuation rules without touching idiom, phrasing, or word choice unless explicitly asked.

---

## Hand-off

Polish is the terminal phase — there is no next phase to invoke regardless of caller.

- **Standalone** (user invoked `/polish` directly): Return the polished text and stop. End the response with: **Done.** Polish is the terminal phase.
- **Pipeline** (invoked from `/shape`): Return the polished text plus a brief summary — count of punctuation corrections, sentences cut, and any notable structural changes made by polish.
