# File Mode — preview changes in plan mode before writing

Shared contract. Any prose-shaper skill that **edits text** follows this when the prose
comes from a file on disk. `assess` is exempt — it only diagnoses, it never writes.

The point: when the prose lives in a file, prose-shaper never overwrites it silently. It
enters plan mode, shows what it will change and why, and writes only after the user
approves. This reuses the harness's native review UI, and because entering plan mode is an
explicit mode switch, the review holds even under `acceptEdits` / `bypassPermissions`.

## When File Mode applies

In effect whenever the prose being shaped was read from a file on disk — the user names or
points to a file path, or you `Read` a file to get the text. Prose pasted directly into
the chat is **not** File Mode: behave as before (return the result in chat; write nothing).

## The loop

1. **Read** the file's current contents.
2. **Shape in memory.** Run the pass(es). Do not `Edit` or `Write` the file yet.
3. **Enter plan mode.** Call `EnterPlanMode`.
4. **Show what + why** in the plan file:
   - the target file path;
   - a **whole-document before→after diff** (the user's chosen grain is approve-all, so
     present the entire document, not a per-edit checklist);
   - the **rationale** — the phase log: register detected, smells addressed, and why each
     class of edit was made.
   For a long document, segment the diff by section but cover the whole file, and add a
   one-line summary count (e.g. "12 edits across 4 sections").
5. **Request approval.** Call `ExitPlanMode`.
6. **On approval:** write the shaped text back to the **same** file, then confirm the path
   and a short summary of what changed.
7. **On reject or "adjust":** revise in memory and re-present. Never write unapproved text.

## Override

If the user explicitly asks to skip the preview ("just edit it", "apply directly", "don't
show me the diff"), write the file without entering plan mode. The preview is the default,
not a lock.

## Edge cases

- **Pipeline (`/shape`):** run all phases in memory first, then enter plan mode **once**
  with the final diff — do not enter plan mode between phases.
- **Nothing to change:** if a pass finds no improvements, say so and do not enter plan mode
  or write the file.
- **Multiple files:** present one plan per file, or a combined plan clearly segmented by
  path; write each only after its changes are approved.
- **Quotes, code blocks, tables:** unchanged by the editing phases, so they appear
  unchanged in the diff.
