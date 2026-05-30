# Rhetorical Figures Index

A catalog of ~30 named rhetorical figures sourced from Mark Forsyth's *The Elements of Eloquence*. Each figure lives in `figures/<name>.md`. Load only the figure(s) you need — this index is here so you can choose.

> **Forsyth's warning, paraphrased.** Any figure overused, or used in the wrong place, becomes a fault. Persuasive figures in a neutral ADR read as preening; in a meeting note, as defensive. Use one figure where it earns its place. Never stack three in a paragraph. The figure should disappear into the argument, not stand on top of it waving.

The register gate from `SKILL.md` still applies — none of these figures belong in technical, neutral, or status-report prose. Each figure file's frontmatter `description` names the cases where even persuasive prose should skip it.

A note on naming collisions. Forsyth's chapter "Prolepsis" describes the *grammatical* device of using a pronoun before its noun. The `craft` skill's "prolepsis" is the *rhetorical* sense — preempting the reader's objection — and lives in `rhetorical-moves.md`. They share a name, not a meaning. Antithesis is also covered in `rhetorical-moves.md` and has no figure file here.

---

## How to use this index

Scan the "Reach for it when…" column to shortlist figures that match the problem you're trying to solve. Some rows carry an italic *Skip if…* hint — a one-line failure condition. If the hint clearly applies to the prose at hand, reject the figure here and don't load its file. Otherwise load only the figure files you shortlisted (`figures/<name>.md`) for the full `description` (the discovery hook in YAML frontmatter, mirroring SKILL.md's format), definition, and example. Most craft passes will not need this catalog — the six core moves cover most edits.

For programmatic filtering, every figure file's frontmatter carries `group` (one of: `repetition`, `balance`, `sound`, `sentence-shape`, `trope`). `grep -l "group: trope" figures/*.md` returns all trope figures, for instance.

---

## Repetition (chain, frame, hammer)

| Figure | Reach for it when… | File |
|---|---|---|
| Anaphora | Several sentences share a subject and need cumulative, relentless weight. | `figures/anaphora.md` |
| Epistrophe | A list of clauses should land on the same outcome word. | `figures/epistrophe.md` |
| Epizeuxis | One word, hammered, must override the rest of the page. *Skip if you've already used it in this doc — once per document, max.* | `figures/epizeuxis.md` |
| Diacope | A line should read like a slogan — Bond, James Bond. | `figures/diacope.md` |
| Anadiplosis | A causal chain feels speculative and needs to feel inevitable. *Skip if any link is weak — the form invites scrutiny that collapses the sentence.* | `figures/anadiplosis.md` |
| Epanalepsis | One closing sentence should circle back to its opening word. *Skip in most cases — hard to land without sounding aphoristic-written.* | `figures/epanalepsis.md` |
| Polyptoton | Repetition would help but the same word twice would tire the ear. | `figures/polyptoton.md` |

## Balance (mirror, parallel, contrast)

| Figure | Reach for it when… | File |
|---|---|---|
| Chiasmus | A pivot sentence should reframe the problem in the shape of the sentence. *Skip if the second half cannot genuinely reverse the meaning — pure mirror without insight is the most embarrassing figure here.* | `figures/chiasmus.md` |
| Isocolon | Three peers should land with equal weight. | `figures/isocolon.md` |
| Tricolon | The third item can pay back the rhythm of the first two. | `figures/tricolon.md` |
| Merism | "Everyone" or "everything" feels abstract; named parts make it concrete. | `figures/merism.md` |

## Sound

| Figure | Reach for it when… | File |
|---|---|---|
| Alliteration | A name, headline, or one line must stick. | `figures/alliteration.md` |
| Assonance | A line already carries weight and you want a subtle sonic binder. *Skip if you can hear it deliberately — it's too loud; let it emerge instead.* | `figures/assonance.md` |

## Sentence shape

| Figure | Reach for it when… | File |
|---|---|---|
| Periodic Sentence | The setup IS the argument and the conclusion should feel earned. | `figures/periodic-sentence.md` |
| Hyperbaton | The word that should land is buried in the middle of the natural sentence. *Skip if the inversion would force the reader to re-parse the sentence.* | `figures/hyperbaton.md` |
| Parataxis | A sequence should feel like a sequence — no subordination. | `figures/parataxis.md` |
| Hypotaxis | A single thought genuinely has dependencies you cannot break apart. | `figures/hypotaxis.md` |
| Aposiopesis | A stake the reader already feels can finish itself in their head. *Skip if you've already used it once in this doc — twice is just unfinished writing.* | `figures/aposiopesis.md` |
| Scesis Onomaton | A scene or status needs atmosphere faster than full sentences can deliver. | `figures/scesis-onomaton.md` |

## Trope (meaning-shift)

| Figure | Reach for it when… | File |
|---|---|---|
| Litotes | Direct praise sounds like marketing; direct criticism, like blame. | `figures/litotes.md` |
| Hyperbole | The honest number is smaller than the felt experience. *Skip in any prose where the reader expects precision — never in ADRs or data-heavy memos.* | `figures/hyperbole.md` |
| Adynaton | Plain "never" sounds bureaucratic and a specific impossibility would land. *Skip in formal documents and board memos — anywhere the reader expects you to mean what you say.* | `figures/adynaton.md` |
| Personification | An abstract concept should feel like a force, not a topic. | `figures/personification.md` |
| Synaesthesia | A cross-sensory image will catch a reader who has stopped reading carefully. *Skip unless you are clearly in opinion or marketing register — never in technical or professional prose.* | `figures/synaesthesia.md` |
| Catachresis | The standard word is too tame and you want the reader to flinch. *Skip unless you are in op-ed or polemic — reads as a typo in an ADR.* | `figures/catachresis.md` |
| Transferred Epithet | Literal phrasing is flat; a displaced adjective makes the scene vivid. | `figures/transferred-epithet.md` |
| Syllepsis | One word can carry both a literal and figurative sense for a quotable line. *Skip in formal argument — the wit undermines the gravity a serious case requires.* | `figures/syllepsis.md` |
| Zeugma | Three near-identical sentences can compress to one shared verb. | `figures/zeugma.md` |
| Paradox | A familiar claim needs to feel new by attacking the reader's first reading. *Skip if the contradiction is only verbal with no underlying truth — that's just a confused sentence.* | `figures/paradox.md` |
| Rhetorical Question | A section transition should feel like the reader reached the conclusion. | `figures/rhetorical-question.md` |
| Congeries | The reader has been minimizing; a pile-up must make minimization impossible. | `figures/congeries.md` |

---

> **Load-on-demand.** This index is the entry point. Load it to discover; load individual figure files for full guidance. Do not load every figure file at once — the catalog is too long to be useful as a single context blob.
