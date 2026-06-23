# LEARNINGS — Day 23

## What I set out to test

Could Claude act as a genuinely useful (not just enthusiastic) startup advisor — one that would tell me "this is harder than it looks" instead of cheerleading a business idea? And could it back that judgment with real data and turn it into professional, shareable documents rather than just a long chat reply?

---

## What worked well

1. **Structured intake before generation.** Asking the 7 standard questions (idea, problem, customer, motivation, validation, market, ambition) *before* generating anything forced clarity I didn't have when I first described the idea in one line. This mirrors how real accelerators (YC, etc.) actually run first-pass diligence.

2. **Research-backed numbers, not vibes.** Claude pulled real figures — India's 86% small/marginal farmer statistic, the 18,800+ Custom Hiring Centres, the actual funding history of EM3 Agri Services — instead of inventing plausible-sounding statistics. Where no clean number existed (an India-only rental market size), it built a bottom-up estimate and *explicitly labeled it as a hypothesis to validate*, not a fact. That distinction matters a lot and is easy for a model to blur if you don't ask for it directly.

3. **The verdict was honest, not flattering.** Founder-Market Fit scored 3.6/10. The competitive analysis flagged that an OEM-backed leader and a free government program already serve this exact customer. That's not what I wanted to hear, but it's the entire point of running a validation exercise — a report that only confirms what I already believed would have been worthless.

4. **Documents as code, not as prose.** Generating the `.docx` files programmatically (via the `docx` npm library) instead of asking Claude to "write a report" in chat meant I got real tables, color-coded scorecards, page numbers, and embedded charts — output I can actually hand to someone, not a wall of markdown.

5. **Re-using its own output as input.** In a later step, Claude was handed its own earlier report as an uploaded file and asked to extract structured fields (idea/problem/competitors/insights) from it before generating a second document. It parsed its own prior output correctly and used it as grounding — useful for any multi-stage workflow where you want to feed yesterday's output into today's task.

---

## What I'd do differently next time

- **Validate the per-farm spend assumption immediately**, rather than after the report is built. The TAM/SAM/SOM number is only as good as that one assumption, and it's the first thing a sharp investor would poke at.
- **Push for primary research earlier in the process.** The biggest score drag across both documents (Founder-Market Fit, Customer Clarity, MVP Readiness) was the same root cause: zero direct farmer interviews. No amount of secondary research fixes that — it's the actual next action, not a nice-to-have.
- **Ask for a one-page version earlier.** The 18-page validation report is great for deep diligence; the 4-page MVP blueprint turned out to be far more useful for actually deciding what to build first. Next time, I'd request the short version first and only go deep on sections that need it.

---

## Reusable pattern for future days

This is a template I can reuse for *any* future idea I want to pressure-test before committing time to it:

1. Answer the 7-question intake honestly (don't pre-soften the idea).
2. Ask for the 18-page validation report (or just the FMF + Competitor + Go/No-Go sections if short on time).
3. Ask for the 4-page Customer & MVP Blueprint *before* writing any code.
4. Treat every "illustrative" or "bottom-up estimate" number as a to-do, not a fact.
5. Execute the 30-Day Action Plan / Founder Action Sheet exactly as written — the report is only as useful as the validation it triggers afterward.

---

## Tools / techniques used today

- Claude web search (live market data retrieval, multi-source triangulation)
- Claude code execution (`docx` npm library, `matplotlib`, LibreOffice headless PDF conversion)
- Document-as-code generation pattern (build script → validate → convert → QA render → deliver)
- File upload + extraction (Claude reading its own prior `.docx` output as structured input)

**#ABTalks60DayChallenge — Day 23 of 60**
