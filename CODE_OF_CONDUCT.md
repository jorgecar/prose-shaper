# Code of Conduct

These rules apply to anyone interacting with the prose-shaper repository — issue authors, PR submitters, reviewers, maintainers, and any agent acting on a contributor's behalf.

## For human contributors

- Assume good faith. Critique the work, not the person.
- No harassment, personal attacks, or discriminatory language. This includes language about race, gender, sexuality, disability, religion, nationality, or appearance.
- Debates about prose, register, and rhetorical choices are welcome. Debates about contributors are not.
- Disagreement is fine; sustained hostility is not. If a thread is going sideways, step back before posting.
- To report a concern, open an issue with the label `conduct`. Redact specifics if you need to — a maintainer will follow up before any details become public.
- Maintainers may edit, close, or lock issues and PRs, and may block accounts, for repeated or severe violations.

## For agent contributors and their human submitters

Agents (Claude, Copilot, and others) contribute substantively to this repository.

- Every agent-authored PR is submitted by a human, who is accountable for what it contains. The conduct rules above apply to the submitter — not to the agent — and so does any maintainer response to a violation.
- Agent-authored work follows the engineering norms already in the repo:
  - `CLAUDE.md § Commit messages` — conventional-commits prefix, one concern per commit, no source or author references in git history.
  - `CLAUDE.md § Extending the plugin` — audit existing coverage before adding; keep the plugin thin; mirror SKILL.md frontmatter for reference content.
  - `CLAUDE.md § Documentation` — match peer-entry texture in `CHANGELOG.md`, `ATTRIBUTION.md`, and the README.
  - `CONTRIBUTING.md § Integrating a new source` — the seven-phase playbook (scope → shape → build → integrate → verify → dogfood → document).
  - `ATTRIBUTION.md` — **no verbatim text from copyrighted works**; examples must be original constructions.
- Before opening a PR that touches prose, run the plugin's own dogfood pass on the new prose (per `CONTRIBUTING.md § 6 Dogfood`). A draft that fails those rules is not ready for review.

## Scope and revisions

These rules cover issues, pull requests, discussions, and any other space tied to the repository. Maintainers may revise them; substantive changes land in `CHANGELOG.md` under the release in which they ship.
