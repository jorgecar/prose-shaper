# CLAUDE.md — prose-shaper

## Commit messages

Describe the plugin's technical impact, not the source material or research that informed the change.

- **Subject**: imperative, ≤ 70 chars, conventional-commits prefix (`feat(scope):`, `style(scope):`, `docs:`, `fix(scope):`, `chore:`).
- **One concern per commit.** Isolate refactors, style cleanups, and feature work — never bundle.
- **Body** (optional): bullets or short paragraphs describing what changed in the codebase — file paths, structural changes, behavior changes.
- **Do not include**: book titles, author names, the reading list or research that inspired the change, conversation context, "this was suggested by X" framing. Those belong in `CHANGELOG.md`, `ATTRIBUTION.md`, or the PR body — never in git history.

Bad: `feat(craft): add Forsyth rhetorical figures catalog (load-on-demand)`
Good: `feat(craft): add load-on-demand catalog of 30 rhetorical figures`
