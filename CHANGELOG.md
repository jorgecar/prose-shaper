# Changelog

All notable changes to prose-shaper will be documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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
