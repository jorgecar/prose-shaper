# Contributing to prose-shaper

This file is the contributor process doc. Its content is the source-integration playbook below — the workflow for adding reference books (such as Williams' *Style: Lessons in Clarity and Grace* and Forsyth's *The Elements of Eloquence*) into the plugin. Other contributor concerns (PR process, dev setup, testing notes) can land here later.

See also: `CLAUDE.md` for the always-loaded project norms (commit messages, extending the plugin, documentation discipline, project scope).

---

## Integrating a new source

Use this when adding a reference book or article as an influence on one or more phase skills. The playbook has six phases. Each phase cites a prior-art example so a fresh-context agent or a new contributor can mirror the shape.

### 1. Scope

Audit every chapter or section of the source. Classify each as:

- **NEW** — relevant to a phase; not already covered by the plugin or another source already integrated.
- **REDUNDANT** — already covered (Strunk on clarity, Williams on cohesion, etc.).
- **OUT-OF-SCOPE** — poetic, register-mismatched, or decorative; doesn't fit the plugin's prose registers.

For long sources, spawn an Explore-style subagent; give it the chapter list and existing skill coverage; ask it to classify each chapter in one line. Then decide what's in. **Bias thin** — coverage that duplicates existing material is worse than nothing.

Prior art: the Forsyth audit (39 chapters; ~30 kept; the rest skipped as redundant, register-mismatched, or naming collisions).

### 2. Shape

For each surviving piece from phase 1, decide where it lives. Three options; mix freely:

| Option | When to use | Example |
|---|---|---|
| New procedure step in `skills/<phase>/SKILL.md` | The technique is core to the phase and every pass should consider it | Cohesion + sentence-shape steps in `flow/SKILL.md` |
| Always-loaded `skills/<phase>/references/<name>.md` | A small, always-relevant reference one or two procedure steps depend on | `flow/references/cohesion.md`, `flow/references/sentence-shape.md` |
| Load-on-demand per-item catalog under `skills/<phase>/references/<group>/` | The source is a list of discrete items the agent picks from | 30 figures under `craft/references/figures/` with an index at `craft/references/rhetorical-figures.md` |

Decide the shape before you write — it determines everything that follows.

### 3. Build

Write the content. These rules also live in `CLAUDE.md § Extending the plugin`:

- **Mirror SKILL.md frontmatter** for per-item catalog files. Each file's YAML carries `name`, `group`, and a `description` (does + when-to-use + when-not + keywords) — same shape as a SKILL.md description, so the agent discovers items the same way Claude discovers skills.
- **Every frontmatter field must earn its place.** If the `description` already carries it, the field is duplicative.
- **All examples are original.** No verbatim text from copyrighted works. `ATTRIBUTION.md` opens with this rule; honor it.
- **Verify definitions against the source.** Spawn a fresh-context subagent to read the source and check each definition against your draft — cheap insurance, catches divergences before they ship.

Prior art: `skills/craft/references/figures/anaphora.md` — per-item file with mirrored frontmatter; `skills/flow/references/cohesion.md` — always-loaded reference.

### 4. Integrate

Wire the new content into the skill. A reference file isn't done until SKILL.md mentions when to reach for it.

- **New procedure step:** add it to `skills/<phase>/SKILL.md` in the right slot.
- **New reference file:** add a pointer paragraph after the reference table (or wherever existing pointers to `references/*.md` live).
- **Catalog:** add an index file (the entry point the agent reads first) plus a pointer from SKILL.md to the index. Add `*Skip if…*` hints to the index for high-rejection items so the agent can reject from the row alone without loading the file. A skip-if hint earns its place when an item has a clear failure condition the agent can check against the prose at hand.

Prior art: `craft/SKILL.md` procedure step 9 + the reference paragraph after the six-move table; `craft/references/rhetorical-figures.md` index with skip-if hints on 13 of 30 figures.

### 5. Verify

Spawn a fresh-context subagent on a representative draft for the target phase. Confirm:

- The skill triggers correctly (register gate passes or skips as expected).
- The new material gets used where it fits.
- Load efficiency is reasonable — the agent should not load the full catalog if a row-level decision suffices.

If the agent over-loads or picks the wrong item, iterate on the index entries and skip-if hints. Re-test until the same draft produces a clean, efficient run.

Prior art: the two end-to-end tests for the figures catalog — the first run showed the agent could discover figures via the index; the second (after adding skip-if hints) rejected 4 figures from the row alone and shortlisted 10 figures vs. 2 the first time.

### 6. Document

Three files touch in this order:

1. **`ATTRIBUTION.md`** — add a one-line bullet under "Influences (Not Verbatim)" matching peer-entry length. Don't explain the use.
2. **`CHANGELOG.md`** — add entries under `[Unreleased]` in the existing sections (Added / Changed / Attribution). Match the texture of peer entries. Describe what the user gets, not how it's wired.
3. **Commit** per `CLAUDE.md § Commit messages` — technical, plugin-impact, isolated per concern, **no source or author refs in commit messages**. Source attribution lives in `ATTRIBUTION.md` and `CHANGELOG.md`, never in git history.

Optional: extend `evals/per-skill/<phase>.json` with use cases that exercise the new material. Worth doing if the integration adds a triggering pattern or covers a register/genre missing from existing evals.
