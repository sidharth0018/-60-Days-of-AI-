# Day 48 — Learnings

## 1. MCQ-gated interviews are a reusable prompt pattern
The "ask one MCQ at a time, don't generate anything until all questions are
answered" pattern is portable to any comparison/decision tool: job offers,
laptops, cities to relocate to, tech stacks. The pattern has 5 reusable slots:

1. **Category + 4 example options** — forces concreteness early
2. **Audience + single decision** — keeps scope tight
3. **≥4 measurable criteria** — prevents vague "which is best" scoring
4. **Sourcing method** — decide upfront whether data is user-provided,
   AI-researched, or a mix
5. **Fixed vs weighted ranking** — decides the core interactivity model

Answering these as single-tap MCQs (not free text) made the whole spec-gathering
phase take under a minute of actual typing.

## 2. Sourced-fact vs estimate separation needs to be structural, not just a caveat
Early comparison tools I've seen (and built) tend to bury a disclaimer at the
bottom: "note: some figures are estimates." That's easy to miss and doesn't
help the user know *which* numbers to trust.

This build instead tags every individual data point inline (`estimate` badge)
and gives estimates their own explanation in the "How this was researched"
panel. The lesson: **transparency has to live next to the number it qualifies,
not in a footer.**

## 3. Research conflicts are useful content, not noise
While researching, sources disagreed on:
- IBM's course count (8 vs 9 vs 11, depending on when the source was published)
- Google's monthly price ($49 vs $59 across two Coursera-adjacent pages)
- upGrad's program fee (varies wildly across upGrad's own multiple offerings —
  Advanced Certificate vs Executive PG vs M.Sc.)

Rather than picking one number silently, documenting *why* a number was chosen
(most recent, most frequently cited, closest match to the comparison category)
turned research friction into a trust-building feature of the final product.

## 4. Weighted scoring math kept simple on purpose
Formula used:
