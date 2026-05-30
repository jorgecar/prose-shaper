# CLAUDE.md — prose-shaper

## Commit messages

Describe the plugin's technical impact, not the source or research behind the change.

- **Subject**: imperative, ≤ 70 chars, conventional-commits prefix (`feat(scope):`, `style(scope):`, `docs:`, `fix(scope):`, `chore:`).
- **One concern**: isolate refactors, style cleanups, and feature work — never bundle.
- **Body** (optional): bullets or short paragraphs describing what changed — file paths, structural changes, behavior changes.
- **Do not include**: book titles, author names, the reading list or research that inspired the change, conversation context, "this was suggested by X" framing. Those belong in `CHANGELOG.md`, `ATTRIBUTION.md`, or the PR body — never in git history.

Bad: `feat(craft): add Forsyth rhetorical figures catalog (load-on-demand)`
Good: `feat(craft): add load-on-demand catalog of 30 rhetorical figures`

## Extending the plugin

Keep the plugin thin. Audit existing coverage before adding; prefer extending one phase deeply over spreading shallow coverage across phases. Push advanced or specialized material to load-on-demand `references/`; never bloat always-loaded SKILL.md.

When adding reference content the agent will navigate (figures, smells, moves, genre packs):

- **Mirror SKILL.md frontmatter.** Each file's YAML carries `name`, `group`, and a `description` (does + when-to-use + when-not + keywords) — same shape as SKILL.md, so the agent discovers items the same way Claude discovers skills.
- **Every frontmatter field must earn its place.** Don't add fields for completeness or attribution traceability. If the `description` already carries it, the field is duplicative.
- **Integrate, don't drop.** A new `references/` file isn't done until the SKILL.md procedure mentions when to reach for it and pointer paragraphs explain the discovery flow.

Full workflow for integrating a new reference source: see `CONTRIBUTING.md § Integrating a new source`.

## Documentation

In `CHANGELOG.md`, `ATTRIBUTION.md`, and the plugin/README descriptions: match the length and texture of existing peer entries. Describe what changed for the reader, not how it was wired. Skip implementation detail (file paths, frontmatter schemas, "and ~27 others" counts) unless a peer entry sets that precedent.

## Project scope

prose-shaper serves any prose context — essays, fiction, journalism, business — not just business writing. Positioning, examples, and future genre files should reflect this scope. The pipeline is register-agnostic; only `craft` gates on persuasive register.
