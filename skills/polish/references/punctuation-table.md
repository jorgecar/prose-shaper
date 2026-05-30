# Punctuation Table

Full reference for `prose-shaper:polish`. The SKILL.md carries an abbreviated 6-row version; this table covers all 12 rules.

| Rule | Wrong | Good |
|---|---|---|
| Oxford comma | "APIs, webhooks and events" | "APIs, webhooks, and events" |
| Comma after introductory phrase | "After the migration the system stabilized." | "After the migration, the system stabilized." |
| Comma before coordinating conjunction (independent clauses) | "The API returned an error and the request was dropped." | "The API returned an error, and the request was dropped." |
| Colon introduces explanation or list | "The problem was; a missing index." | "The problem was clear: a missing index." |
| Semicolon connects related independent clauses | "The API returns JSON: it doesn't support XML." | "The API returns JSON; it doesn't support XML." |
| Hyphen for compound modifiers before noun | "A well known issue" | "A well-known issue" — no hyphen after the noun: "the issue is well known" |
| En dash for ranges | "Pages 1-5" | "Pages 1–5" |
| Em dash for interruption or strong aside | "The fix - which took three days - shipped Friday." | "The fix — which took three days — shipped Friday." |
| Parentheses de-emphasize; em dashes emphasize | "The delay (three weeks) was critical." | "The delay — three weeks — was critical." (if critical) |
| Ellipsis: almost never in professional prose | "We considered many options..." | "We considered many options." — or rewrite to be specific |
| Exclamation marks: 1 max (professional/persuasive); 0 (technical) | "The results are in! The system is stable! Great news!" | "The results are in. The system is stable." |
| Quote punctuation: period inside quotes (American style) | He called it "a blocker". | He called it "a blocker." |

---

## Notes on the harder rules

**Colon vs semicolon** is the most common mistake. Both join independent clauses, but they signal different work. A colon tells the reader that what follows is the essence of what just preceded — the same idea restated, exemplified, or specified. A semicolon tells the reader that what follows is a second complete thought, related to the first but not contained in it; both clauses carry their own emphasis. Test: if what follows could be introduced by *namely* or *that is*, use a colon; if it could be introduced by *meanwhile* or *and*, use a semicolon.

- *Colon:* `The pipeline has one bottleneck: the test suite re-runs unchanged modules.`
- *Semicolon:* `The pipeline re-runs unchanged modules; the cache layer never invalidates.`

**Em dash vs parentheses vs commas** — three settings for an aside, on a single graduated scale of attention. Commas treat the aside as part of the sentence's normal flow; the reader registers it without breaking stride. Em dashes mark the aside as a moment of heightened attention — a beat the writer wants the reader to notice. Parentheses do the opposite: they tell the reader the aside is supplementary and can be skipped without loss. Pick the mark that matches the weight you want the aside to carry.

- *Commas:* `The migration, scheduled for Friday, will rebuild every index.`
- *Em dashes:* `The migration — scheduled for Friday — will rebuild every index.` (the timing is part of the news)
- *Parentheses:* `The migration (scheduled for Friday) will rebuild every index.` (the timing is a footnote)

**Compound modifiers:** Hyphenate before the noun ("a well-known bug"), not after ("the bug is well known"). Never hyphenate `-ly` adverb compounds ("a newly released version").

**Ellipsis in quotes:** Acceptable when indicating that words have been omitted from a direct quote (e.g., "The system… was unstable"). Not acceptable as a trailing mood device.

---

> **Load-on-demand:** This file is a reference. Load it only when the abbreviated table in `SKILL.md` does not cover the rule at hand. Do not load it on every polish pass.
