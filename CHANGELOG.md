# Changelog

All notable changes to prose-shaper will be documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.4.0] — 2026-05-28

### Added

- File Mode: when a draft is read from a file on disk, prose-shaper now enters plan mode to present the whole-document before→after diff and the rationale, and writes the file only after the user approves — pasted-in-chat text is unaffected. Defined once in `skills/shared/file-mode.md`, wired into the `using-prose-shaper` orchestrator and the `clarity`/`flow`/`craft`/`polish` standalone hand-offs (`assess` is exempt — it never edits).

## [0.3.0] — 2026-05-28

### Added

- `flow`: three new procedure steps — "Connect each sentence old-to-new" and "Keep the topic string consistent" (sentence- and passage-level cohesion), and "Shape long sentences" (get to the verb early; extend with resumptive/summative/free modifiers instead of clause-piling). "Map the document" now also frames the opening as a problem (condition + cost) ending on the point.
- `flow`: two reference files — `references/cohesion.md` (old-before-new, topic strings, whole-document coherence) and `references/sentence-shape.md` (long-sentence architecture), with original before/after examples.
- `assess`: two new smells — `topic-drift` (inconsistent topic string) and `sentence-sprawl` (a single over-built sentence) — with full entries in the smell catalog.

### Changed

- `clarity`: the "replace to-be / passive" step now keeps a passive when flipping it would push unfamiliar information to the front (cohesion outranks the active voice).
- `assess`: `buried-lede` and `passive-agent` catalog entries clarified — the point belongs at the end of every opening segment; a passive can be the right choice when it preserves old-before-new flow.

### Attribution

- Added Joseph M. Williams, *Style: Lessons in Clarity and Grace*, as an influence.

## [0.2.1] — 2026-05-27

### Changed

- Each phase skill's standalone hand-off now ends with a one-line recommendation pointing to the next step in the pipeline (`/assess` → `/clarity`; `/clarity` → `/flow`; `/flow` → `/craft` or `/polish`; `/craft` → `/polish`; `/polish` → done). Pipeline-mode behavior is unchanged.

## [0.2.0] — 2026-05-27

### Added

- Worked end-to-end example in `using-prose-shaper` (meeting-note before/after with phase-by-phase log).
- `clarity`: two new procedure steps — "Omit needless words and intensifying adverbs," "Replace jargon and cliches with plain, specific words."
- `flow`: two new procedure steps — "Map the document" (give the reader a map; lead with ownership), "Cut across expectation."
- `craft`: three new procedure steps — "Open at the change" (start late + lead with ownership), "Let dialogue do work," "Small paragraphs as stories."

### Changed

- `flow` is now register-aware: the rhythm-variation step is skipped when `register == technical` (technical prose values uniformity over variation). All other flow steps still apply.

### Fixed

- YAML frontmatter parsing on GitHub: replaced `: ` with ` — ` in 14 places across 6 SKILL.md files where structural colons in description values were tripping GitHub's strict frontmatter parser. Claude Code's permissive parser was unaffected.

## [0.1.0] — 2026-05-26

### Added

- Five-phase prose pipeline: `assess`, `clarity`, `flow`, `craft`, `polish`.
- Meta-skill `using-prose-shaper` orchestrating the pipeline with conditional `craft` based on register.
- Six slash commands: `/shape` (full pipeline) + one per phase.
- Per-skill reference directories with progressive disclosure.
