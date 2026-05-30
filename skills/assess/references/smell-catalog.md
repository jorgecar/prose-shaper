# Smell Catalog

Full definitions and detection rules for the thirteen smell tags used by `assess`.

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

**Detection rule:** Ask: "What is the one thing this document must communicate?" If that thing does not appear in the first two sentences or the opening block, the lede is buried. This applies at every level: the point belongs at the end of the opening segment of the document, and of each section and long paragraph — not only the document's.

---

## `verdict-no-frame`

**Definition:** A strong claim is asserted without evidence, logic, or framing that would let the reader accept or challenge it.

**Example:** "The current architecture is inefficient." / "This approach won't scale."

**Detection rule:** Flag any sentence that delivers a verdict (positive or negative) with no supporting data, no comparison baseline, and no reasoning. A claim that cannot be falsified from the text alone is unframed.

---

## `passive-agent`

**Definition:** The passive voice is used to obscure who is responsible for an action or decision.

**Example:** "It is recommended that the timeline be revised." / "Approval has been granted."

**Detection rule:** Look for "it is [past-tense verb]", "has been [verb]", "will be [verb]" — then ask: by whom? If the answer matters and is missing, flag it. (Note: passive voice is not always a smell — only flag when the missing agent changes meaning or accountability.) Especially, leave the passive when it keeps familiar information at the start of the sentence and new information at the end; that cohesion is worth more than the active voice (see `skills/flow/references/cohesion.md`).

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

## `topic-drift`

**Definition:** Across a run of sentences, the grammatical subjects name an unrelated or constantly shifting set of ideas. Each sentence can be clear on its own, yet the passage feels disorganized because the reader cannot track a consistent topic.

**Example:** "The cache holds responses for 24 hours. Writes don't trigger invalidation. Stale data is what users end up seeing." (subjects: *the cache* / *writes* / *stale data*)

**Detection rule:** Underline the first few words — up to the verb — of each sentence in a passage. If those words don't form a small, related set (and don't name the passage's main characters), the topic string has drifted. Distinct from `wall-of-text`, which is about length and idea-count; `topic-drift` is about subject *consistency*.

---

## `sentence-sprawl`

**Definition:** A single sentence is hard to follow because its main verb arrives late — buried behind a long introductory clause or a long abstract subject — or because it chains one relative clause onto another after the verb.

**Example:** "The proposal that the steering committee drafted after three months of stakeholder interviews and two rounds of legal review, over the finance team's objections, was finally rejected." (nineteen words before the main verb *was rejected*)

**Detection rule:** Flag a sentence when the reader passes roughly eight or more words before reaching the main subject and verb, or when three or more `which`/`that`/`who` clauses hang off the end. Distinct from `wall-of-text` (a whole paragraph of many ideas) and `topic-drift` (subjects shifting across sentences) — `sentence-sprawl` is one over-built sentence.

---

## `ungrouped-supports`

**Definition:** The supporting ideas under a claim don't share a parallel relationship to it. The themes either overlap (two themes restate the same support, padding the case), or they leave a gap (the themes together do not cover what the claim depends on). The reader can follow each support individually but cannot see them as a set that proves the claim.

**Example:** "We should adopt the new build system because it caches dependencies, it parallelizes test runs, it cuts CI time, and it speeds up the pipeline." — The first two themes are causes; the last two are the same effect restated as causes. The supports are not a parallel set.

**Detection rule:** List each section heading or topic sentence under the document's lede (or each support under a paragraph's topic sentence). Ask: do they form a parallel set of supports for the same claim? If two restate one idea, or if the claim depends on something none of them covers, the supports are ungrouped. Distinct from `topic-drift` (sentence-subject scatter across a passage) — `ungrouped-supports` is *idea-grouping* at section scale.

---

## `blank-label`

**Definition:** A section heading or topic sentence names the category of content that follows ("Background", "Issues", "Findings", "There are several considerations") without saying anything about it. The reader who skims headings or first sentences learns the document's table of contents but not its argument.

**Example:** Heading: `Issues with the cache layer.` (Tells the reader what the section is *about*; does not tell them what the section *says*.) Repair: `The cache layer adds two days of work and removes one source of stale reads.`

**Detection rule:** Read the heading or topic sentence alone, with no surrounding context. Does it state a conclusion the reader could agree or disagree with? If not — if it only names a topic — it's blank. A complete-thought summary has a subject, a verb, and a point.

---

## `metadiscourse`

**Definition:** Sentences whose subject is the text itself rather than the world the text is about. The writer announces what they are about to say, recaps what they have just said, or signposts where the document is going — instead of advancing the argument. The reader follows the prose's table of contents instead of its content.

**Example:** "In this section we will outline the three risks. Having considered those risks, we now turn to mitigations." Repair: delete the announcing sentences; let the section's first claim do the work.

**Detection rule:** Flag sentences whose grammatical subject names the text or the writing act (`this section`, `this paper`, `we`, `the author`) paired with verbs of communication (`will discuss`, `argue`, `examine`, `consider`, `turn to`, `have shown`). Distinct from `warm-up`, which is a smell of openings only — metadiscourse can appear anywhere, and most often clusters at section boundaries.

---

## `professional-narcissism`

**Definition:** The writer describes their own research activity — what they studied, what they found, what they conclude — instead of describing the subject directly. The reader learns about the author's process, not the world the writing is supposed to be about.

**Example:** "Our analysis of cache invalidation patterns reveals that stale reads are the dominant failure mode." Repair: "Stale reads are the dominant cache failure mode."

**Detection rule:** Flag sentences whose subject names the writer or the writer's work (`we`, `our analysis`, `this study`, `the present paper`, `our findings`) paired with verbs of inquiry (`find`, `show`, `examine`, `argue`, `conclude`, `reveal`). One use is fine; a pattern is the smell. Distinct from `passive-agent` (the agent is hidden) and `warm-up` (the writer eases into an opening) — here the writer is visible and active, but the subject they study has been pushed off-stage.

---

Load this file when `assess` needs to explain a specific smell to the user.
