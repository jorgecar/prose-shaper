---
name: assess
description: Tells the user what's wrong with their draft before any edits are made. Use whenever the user shares writing and wants a diagnosis — not changes — naming the register (technical / professional / persuasive), audience, intent, and the specific problems (warm-ups, hedging, buried lede, tonal mismatch, weak evidence). Trigger on — "what do you think of this?", "does this land?", "review my draft", "is this the right tone?", "assess this", "gut-check this", "what's wrong here?", "is this any good?". For requests that ask for changes ("fix this", "tighten this", "rewrite this"), prefer /clarity or /shape instead — assess only diagnoses, it never edits. Keywords — assess, diagnose, gut-check, register, audience, feedback, what's wrong, review.
---

# Assess

## Why this phase matters

Register determines every choice that follows. A persuasive paragraph written with technical detachment fails not because the sentences are bad but because the mode is wrong. Before editing anything, name the audience, the intent, and the register — then flag what the prose is doing that contradicts those three facts.

## Output contract

Begin your response with this exact block. The meta-skill parses these tags to decide whether to invoke craft and how to seed downstream phases; if the block is missing or malformed, the pipeline cannot route correctly. The `<assess-meta>` tags (rather than `---`) prevent the block from being parsed as Markdown frontmatter by downstream tools.

```
<assess-meta>
register: <technical|professional|persuasive>
audience: <one line>
intent: <one line>
smells: <comma-separated tags from the smell catalog, or "none">
</assess-meta>
```

Then below the block, write a brief diagnostic report.

## Procedure

1. **Identify the document type** from path, frontmatter tags, or content cues.
2. **Pick a register** using the table below.
3. **Name the audience** in one line — who reads this, what they need.
4. **State the intent** in one line — what the writing must do.
5. **Tag the smells** present from the catalog (see references/smell-catalog.md).
6. **Emit the structured block** + a 3-5 line diagnostic.

## Register Table

| Register | Applies to | Voice cue |
|----------|-----------|-----------|
| **Technical** | ADRs, API docs, integration specs, schemas, code-adjacent prose | Precise, neutral, declarative |
| **Professional** | Meeting notes, check-ins, project updates, onboarding, internal emails | Direct, scannable, complete sentences |
| **Persuasive** | Proposals, stakeholder emails, pitches, escalations, op-eds | Specific, framed, every sentence earns rent |

**Decision rule:** When uncertain, default to Professional.

## Smell catalog (short)

| Tag | What it means |
|---|---|
| `warm-up` | Opening sentence delays the point |
| `hedge` | "Kind of", "might", "perhaps", "we think" |
| `nominalization` | Buried verb in an abstract noun ("did a review of" vs. "reviewed") |
| `buried-lede` | The point lives in the third paragraph |
| `verdict-no-frame` | Claim without evidence ("This is inefficient") |
| `passive-agent` | "It is recommended that" — who recommends? |
| `register-mismatch` | Persuasive moves in a technical doc, or vice versa |
| `cliche` | Stock phrasing that adds nothing |
| `wall-of-text` | One unbroken paragraph carrying many ideas |

See `references/smell-catalog.md` for full definitions and detection rules.

## Edge cases

- **Quotes and direct speech**: Do not flag smells inside quoted material.
- **Tables, schemas, field definitions**: Skip — assess is for prose only.
- **Already-good prose**: Output the structured block with `smells: none` (the literal string `none` is the sentinel for an empty smell list) and a one-line confirmation.

## Caller mode — output and hand-off

`assess` is invoked two ways. Detect the caller and adjust both output format and hand-off behavior accordingly.

- **Standalone** (user ran `/assess` or asked for a diagnosis directly):
  - *Output*: Lead with a human-readable diagnostic (2-4 sentences naming register, audience, intent, and the top smells). Emit the `<assess-meta>` block at the end for completeness.
  - *Hand-off*: Stop here. Do not edit the user's text. If they want edits, they will invoke `/clarity`, `/flow`, `/craft`, `/polish`, or `/shape` next.

- **Pipeline** (the meta-skill `using-prose-shaper` invoked this skill):
  - *Output*: Emit the `<assess-meta>` block first, on its own. A brief diagnostic afterward is optional.
  - *Hand-off*: The meta-skill reads your block and routes to `clarity` next, then `flow`, then conditionally `craft`, then `polish`. You do not chain phases yourself.

If you cannot tell which mode applies from context, default to standalone — the structured block is harmless to a human reader, while the missing diagnostic hurts.
