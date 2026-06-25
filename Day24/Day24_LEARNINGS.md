# LEARNINGS — Day 24

## What I set out to test

Day 23 confirmed the *problem* was real but left the actual business model under-examined. Day 24 tested whether Claude, acting explicitly as a VC/growth advisor rather than a market researcher, could find the structural flaw in the revenue model itself — not just repeat that the market is competitive.

---

## What worked well

1. **Forcing a different lens changed the output.** The same underlying facts (commission on bookings, owner pays, WhatsApp-first GTM) had already been described in Day 23's blueprint without anyone naming disintermediation as a risk. Asking explicitly for "revenue over vanity metrics" and a Business Reality Check ("why do they pay," "biggest monetization risk") is what surfaced it. The lesson: the same data can yield very different insights depending on which question you force the model to answer first.

2. **Chaining a prior report as source-of-truth worked cleanly.** Uploading yesterday's `.docx` and saying "use this as the source of truth" let Claude correctly extract customer/MVP/pricing/GTM assumptions and build directly on them, without re-litigating the entire validation from scratch. This is a reusable pattern for any multi-day project: each day's report becomes tomorrow's structured input.

3. **Reverse SWOT was more useful than a normal SWOT.** Flipping each quadrant (strength → hidden weakness, threat → hidden opportunity) produced sharper insight than a standard SWOT would have — e.g., "the threat of free government CHCs" reframed as "a potential white-label distribution partner" is a genuinely different strategic option, not just a restated risk.

4. **A single proportional metric beats five separate scores.** The Investment Scorecard has five 0–100 numbers, but the report's own conclusion correctly collapsed them into one actionable number to track: % of bookings that repeat *through* the platform. That's the real lesson of a good scorecard — it should point at one thing to go measure, not just summarize.

5. **Hand-authoring the SVG dashboard gave more control than a chart library would have.** Building the visual dashboard as raw SVG meant every panel, proportional score bar, and line of wrapped text could be checked against the PDF formatting rules (no overflow, no shrink-to-fit) and fixed directly — two iterations caught a text-overflow bug and a missing-glyph emoji issue before final delivery.

---

## What I'd do differently next time

- **Ask for the Business Reality Check before anything else, every time.** It's the cheapest part of the report to produce and it's the part that actually changes the rest of the strategy — Section 1 should probably always come before any of the "build a strategy" sections, not alongside them.
- **Test the disintermediation question with a concrete experiment design**, not just flag it as a risk. The report names the right metric (repeat-through-platform rate) but a sharper version would propose the exact mechanism to measure it (e.g., unique referral codes per owner, tracked bookings) rather than leaving it as a future to-do.
- **Render every wide table as a screenshot before finalizing**, not just spot-check a few. One column-width issue in an early draft (text touching the cell border) was only caught by rendering the actual PDF page, not by reading the table definition in code.

---

## Reusable pattern for future days

This is now a 2-stage pattern I can reuse for any new idea:

1. **Day N: Validate the problem.** 7-question intake → Validation Report → Customer & MVP Blueprint. Verdict: is the *pain* real?
2. **Day N+1: Validate the business.** Feed Day N's blueprint back in as source-of-truth → force a Business Reality Check → Business Strategy Report with Reverse SWOT and a single Investment Scorecard. Verdict: is the *model* real?

Skipping straight to Stage 2 without Stage 1 risks optimizing a fee model for a problem that was never confirmed; skipping Stage 2 risks mistaking a validated pain point for a validated company. Both reports are needed, and Day 24 only worked because Day 23 existed first.

---

## Tools / techniques used today

- File upload + extraction (Claude reading its own Day 23 `.docx` output as structured ground truth)
- Document-as-code generation (`docx` npm library → validate → convert via LibreOffice headless → render & QA every page)
- Hand-authored SVG infographic → rasterized with `cairosvg` → embedded as a native image in the PDF
- Reverse SWOT framing as a sharper alternative to standard SWOT

**#ABTalks60DayChallenge — Day 24 of 60**
