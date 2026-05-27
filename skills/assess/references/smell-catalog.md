# Smell Catalog

Full definitions and detection rules for the nine smell tags used by `assess`.

---

## `warm-up`

**Definition:** The opening sentence exists to ease the writer into the topic rather than serve the reader. It restates the subject, describes what the document will do, or provides backstory before delivering value.

**Example:** "In this proposal, we will outline the reasons why the current approach presents challenges and why a new direction may be worth considering."

**Detection rule:** If you can delete the first sentence and the document loses nothing — it's a warm-up.

---

## `hedge`

**Definition:** Language that weakens a claim the writer could make directly. Hedges signal uncertainty where none is warranted, or protect the writer at the reader's expense.

**Example:** "This might perhaps represent a kind of opportunity worth potentially exploring."

**Detection rule:** Flag `might`, `perhaps`, `kind of`, `seems to`, `we think`, `could potentially`, `may or may not`. One hedge per document is fine — a pattern is a smell.

---

## `nominalization`

**Definition:** A verb or adjective converted into an abstract noun, burying the action and adding filler words.

**Example:** "We conducted an analysis of the results" instead of "We analyzed the results." / "made a decision" instead of "decided."

**Detection rule:** Scan for: "made a [noun]", "conducted a [noun]", "did a [noun] of", "provided [noun] on", "performed [noun]". The noun is almost always a verb wearing a costume.

---

## `buried-lede`

**Definition:** The most important claim — the finding, recommendation, or decision — appears late in the document after extended context-setting.

**Example:** Three paragraphs of background, then: "For these reasons, we recommend canceling the project."

**Detection rule:** Ask: "What is the one thing this document must communicate?" If that thing does not appear in the first two sentences or the opening block, the lede is buried.

---

## `verdict-no-frame`

**Definition:** A strong claim is asserted without evidence, logic, or framing that would let the reader accept or challenge it.

**Example:** "The current architecture is inefficient." / "This approach won't scale."

**Detection rule:** Flag any sentence that delivers a verdict (positive or negative) with no supporting data, no comparison baseline, and no reasoning. A claim that cannot be falsified from the text alone is unframed.

---

## `passive-agent`

**Definition:** The passive voice is used to obscure who is responsible for an action or decision.

**Example:** "It is recommended that the timeline be revised." / "Approval has been granted."

**Detection rule:** Look for "it is [past-tense verb]", "has been [verb]", "will be [verb]" — then ask: by whom? If the answer matters and is missing, flag it. (Note: passive voice is not always a smell — only flag when the missing agent changes meaning or accountability.)

---

## `register-mismatch`

**Definition:** The prose uses moves that belong to a different register — persuasive language in a technical spec, casual phrasing in a formal proposal, or clinical detachment in a pitch.

**Example (persuasive in technical):** "This elegant solution will delight developers and transform how teams collaborate." (in an ADR)

**Example (technical in persuasive):** "The system supports n-tier message queuing with eventual consistency guarantees." (in a budget proposal to non-technical stakeholders)

**Detection rule:** After identifying the register, scan for sentences that would fit better in a different register column. Concentration matters — one sentence is a quirk, three is a mismatch.

---

## `cliche`

**Definition:** A stock phrase so overused it carries no specific meaning — it signals the writer stopped thinking and reached for a familiar form.

**Example:** "At the end of the day", "move the needle", "low-hanging fruit", "game-changer", "circle back", "hit the ground running", "deep dive."

**Detection rule:** If the phrase appears in a hundred decks from companies the writer has never worked at, it's a cliche. Replace the test: can you swap in a specific, literal alternative? If yes, the cliche is confirmed.

---

## `wall-of-text`

**Definition:** Multiple distinct ideas are fused into one unbroken paragraph with no visual entry points. The reader cannot skim, reference, or parse individual claims.

**Example:** A 200-word paragraph covering background, rationale, three risks, and a recommendation — without a single break, list, or heading.

**Detection rule:** Flag any prose paragraph over ~80 words that contains more than one logical claim. (Exception: deliberate narrative prose where flow is the goal — but flag it anyway if the document type is professional or technical.)

---

Load this file when `assess` needs to explain a specific smell to the user.
