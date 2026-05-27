---
name: using-prose-shaper
description: Turns rough writing into prose someone would actually send. Use whenever the user shares a full draft (email, ADR, memo, pitch, release note, announcement) and wants it reworked top-to-bottom — not just one aspect tightened. Trigger on: "shape this", "rewrite this draft properly", "fix this top to bottom", "give this the full pass", "make this sendable", "improve the whole thing", "rework this from scratch", or any request to comprehensively rework a draft. Five passes run under the hood (assess → clarity → flow → craft → polish), but the user only pastes the draft. For single-phase requests ("just tighten this", "just polish this", "just smooth the flow"), prefer the targeted phase skills instead. Keywords: shape, rewrite, full pass, full treatment, end-to-end edit, top to bottom.
---

# Using Prose Shaper

## Overview

prose-shaper takes a rough draft and gives back prose the user would actually send. Five passes run under the hood — diagnose, tighten, smooth, sharpen, proof — invoked together via `/shape`, or one at a time when the user already knows what's broken.

## Decision Tree

```
Need to improve prose?
├── Starting from a rough draft? → /shape (full pipeline)
├── Just want a diagnosis, no edits? → /assess
├── Know it's wordy or hedged? → /clarity
├── Sentences feel choppy or unbalanced? → /flow
├── Needs to move or persuade? → /craft  (persuasive register only)
└── Almost final, just needs a scan? → /polish
```

## Pipeline

```
[assess] → emit structured output block
     ↓
[clarity] → cut filler, nominalizations, weak verbs
     ↓
[flow] → rhythm, parallelism, weight-last
     ↓
[craft]? → persuasive moves (skip if register != persuasive)
     ↓
[polish] → punctuation, final scan
```

## Chaining Contract

`assess` emits a structured block at the top of its response, wrapped in `<assess-meta>` tags:

```
<assess-meta>
register: <technical|professional|persuasive>
audience: <one line>
intent: <one line>
smells: <comma-separated tags, or "none">
</assess-meta>
```

### How to parse the block — explicit runbook

Do not paraphrase or summarize the block. Read it line by line and act on the literal values.

1. Locate the `<assess-meta>` opening tag in the assess output. Read each subsequent line until `</assess-meta>`.
2. Find the line beginning with `register:`. Strip whitespace. Compare the value to the literal string `persuasive`.
3. If the value is exactly `persuasive`, mark craft as ENABLED. If the value is anything else (including missing, malformed, or unexpected), mark craft as SKIPPED and prepare the skip message.
4. The other lines (`audience`, `intent`, `smells`) are informational — pass them into each phase's context, but do not gate on them.

### Phase routing

- `clarity`, `flow`, `polish`: always run, in order. Never skip these.
- `craft`: run only if `register == persuasive` per the rule above. Otherwise emit `"Craft skipped — register: <value>"` and proceed to polish.

### What each phase receives

Each phase operates on the **text** output of the previous phase, not on commentary or diagnostics:

- `clarity` receives the user's original text plus `register` and `audience` as context.
- `flow` receives the clarity-edited text.
- `craft` (if enabled) receives the flow-edited text.
- `polish` receives the craft-edited text if craft ran, otherwise the flow-edited text.

The `<assess-meta>` block is metadata. It is read once by this skill to make routing decisions. It is not passed into the editing phases as material to revise.

## Operating Behaviors

1. Never rewrite quotes, direct speech, or stakeholder decisions verbatim.
2. Never apply craft moves to schemas, code-adjacent prose, or technical documents.
3. When register is ambiguous, default to `professional`.
4. Each phase produces output the next phase consumes — do not skip phases except `craft`.
5. If a phase finds nothing to improve, say so explicitly. Do not manufacture changes.
6. Preserve the author's meaning. The pipeline improves form, not content.
7. Show changes inline or as a diff when the text is short enough to read. For long texts, show a before/after summary per phase.

## When NOT to Use

- Quoted speech or verbatim stakeholder decisions
- Constrained formats: Jira ticket summaries, commit messages, frontmatter fields
- Tables, schemas, field definitions, code blocks
- Brand-mandated copy already approved for publication

## Output Format

After the full pipeline, return:

```
## Shaped Text

<final polished text>

## Phase Log

- assess: <register detected, key smells>
- clarity: <what was cut or rewritten>
- flow: <what was restructured>
- craft: <moves applied, or "skipped — register: professional">
- polish: <issues caught, or "no issues found">
```
