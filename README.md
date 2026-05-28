# prose-shaper

**Rough drafts to ready-to-send prose — in one command.**

```
   ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐
   │ assess  │ ▸ │ clarity │ ▸ │  flow   │ ▸ │ craft*  │ ▸ │ polish  │
   └─────────┘   └─────────┘   └─────────┘   └─────────┘   └─────────┘
    diagnose      tighten       smooth        sharpen       proof
```

> `*` craft runs only when the register is persuasive

The email you didn't have time to rewrite. The ADR that reads like a memo. The pitch that buries the point on line four. Paste it, run `/shape`, and get back something you actually want to send.

Works on emails, docs, ADRs, pitches, fiction — any prose where the words matter more than the format.

## Install

```
/plugin marketplace add jorgecar/prose-shaper
/plugin install prose-shaper@prose-shaper
```

## Quick start

Paste your draft and run:

```
/shape
```

Or call a single phase:

```
/clarity      # tighten verbs and cut filler
/polish       # final punctuation + scan
```

## Working with files

Point any command at a file instead of pasting, and prose-shaper won't overwrite it
silently. It shapes the draft, then opens **plan mode** showing the whole-document
before→after diff and why each change was made — it writes the file only after you approve.
This holds even in auto-accept mode. Pasting text into chat works exactly as before.

## What you get

| When you need to... | Run this | What changes |
|---|---|---|
| Send the whole draft out **today** | `/shape` | Rough text comes back tight, structured, ready to send |
| Know what's wrong **before** you rewrite | `/assess` | A diagnosis — tone, audience, what's broken. No edits. |
| Cut a draft that's **too long** | `/clarity` | Warm-ups gone, hedges cut, weak verbs replaced |
| Smooth prose that reads **choppy** | `/flow` | Sentences that connect, consistent topic, variety, key word at the end |
| Sharpen a pitch that **doesn't land** | `/craft` | Rhetorical moves added — when you need to move someone |
| Catch the last things **before send** | `/polish` | Punctuation cleaned, every sentence earning its place |

## How it works

prose-shaper runs your draft through five passes, each fixing one kind of problem:

1. **assess** — names the register (technical, professional, persuasive), audience, and intent. Flags the smells.
2. **clarity** — cuts warm-ups, hedging, nominalizations; trades "to be" for action verbs.
3. **flow** — connects each sentence to the last, keeps a consistent topic string, varies sentence length, shapes long sentences, and moves the heaviest word to the end.
4. **craft** — applies persuasive moves (skipped automatically if the register isn't persuasive).
5. **polish** — fixes punctuation and runs a final scan where every sentence earns rent.

`/shape` runs all five. The single-phase commands (`/clarity`, `/flow`, etc.) skip straight to the pass you need.

## Phrases that trigger it

```
Shape this from scratch.        → /shape
Assess this email.              → /assess
Tighten this paragraph.         → /clarity
Improve the flow of this.       → /flow
Make this pitch sharper.        → /craft
Polish this draft.              → /polish
```

For reliable activation, prefer the slash commands above — Claude doesn't always auto-trigger skills on description match alone.

## Contributing

Issues and PRs welcome at [github.com/jorgecar/prose-shaper](https://github.com/jorgecar/prose-shaper). The plugin practices what it preaches — drafts should run through `/shape` before review.

## License

Apache 2.0. See `LICENSE`. Examples derived from external sources are credited in `ATTRIBUTION.md`.
