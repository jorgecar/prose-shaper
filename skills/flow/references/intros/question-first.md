---
name: question-first
description: Opens with the Question itself, then the Situation, the Complication, and the Answer last. Reach for it when the question is the hook — FAQ entries, RFCs, public-facing posts, anything the reader landed on because they were already asking that question. The form mirrors how they arrived at the document. Avoid when the question is obvious or trivial; opening with an obvious question reads as a rhetorical setup the reader has to wait through. Keywords — question-first, FAQ opener, RFC opener, public-facing, hook question.
---

# Question First

The problem this solves: in formats where the reader arrived because they were already asking a question — they searched for it, they clicked an FAQ link, they opened an RFC about a specific decision — opening with anything other than that question makes the reader hunt for confirmation that they're in the right place. Naming the question first confirms it instantly.

**Pattern shape.**

- **Question** — stated literally, as a question.
- **Situation** — the context that makes the question coherent.
- **Complication** — why the question is worth asking now (sometimes folded into the situation).
- **Answer** — your point, with the reasoning that follows.

**Example.**

- Wrong (Standard SCQA on an FAQ entry): The platform supports several authentication mechanisms, including OAuth, SAML, and API tokens. Customers have asked about session lifetime in each case. The default session lifetime is twelve hours.
- Good (Question First): How long does a session last? Twelve hours by default — and the limit is the same across OAuth, SAML, and API tokens. You can lower the limit per workspace; you cannot raise it without contacting support.

The Good version names the question the reader brought to the page. The answer follows immediately, with the constraints the reader needs to act on it.

**When it works.** FAQs, RFCs (where the title is usually the question), help-center articles, blog posts framed around a single question, any document the reader arrived at by searching for that question.

**When it backfires.** The question is obvious or implicit in the title — opening with it is redundant. The question is a setup the reader hasn't yet thought to ask — they will treat it as rhetorical and skim past. Long-form arguments where the question needs grounding before it can be asked usefully.
