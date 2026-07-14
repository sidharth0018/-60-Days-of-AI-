# Day 44 — LinkedIn Roast & Rebuild Engine

**Challenge:** ABTalks 60-Day Claude AI Mastery Challenge
**Day:** 44 / 60
**Domain:** Personal branding / career growth (Data Analyst job search track)

## What I built

An AI-powered "LinkedIn Optimization Expert" prompt system that audits a real LinkedIn profile section-by-section, scores it, rewrites it, and packages the output as a single interactive HTML report — not just a wall of text.

The system prompt casts Claude as an ex-recruiter who has reviewed 50,000+ profiles, and enforces a strict pipeline:

1. Collect profile inputs one field at a time (headline, About, top Experience entry, skills, target goal)
2. **Roast** — score every section out of 10, quote the user's own words back at them, explain the recruiter's real reaction and the invisible cost of the current wording
3. **Rebuild** — rewrite every section with 3 headline options (keyword / value-prop / authority), a structured About rewrite (hook → story → proof → CTA), before/after bullet pairs for Experience, and a prioritized skills add/remove/pin list
4. **Scorecard** — before vs after score per section, plus an overall score
5. **7-day activation plan** — concrete daily actions (not just profile edits): a rebuild announcement post, targeted connection requests with a message template, a "value comment" formula, a second post, and a numbers-review day
6. **Summary card** — a shareable "before/after" recap formatted for reposting

## Why this design

- **No fabrication rule** — the prompt explicitly forbids inventing achievements, metrics, or projects the user didn't provide. When the user's Experience section had no real deliverable to point to yet, the rebuild flagged that gap instead of making up a number — and called out that closing that gap is the single highest-leverage next step.
- **Interactive HTML over plain text** — turned the multi-part output (roast / rebuild / plan / summary) into a tabbed report with copy buttons on every rewritten block and an expandable 7-day checklist, so it's actually usable rather than a scroll-and-lose-your-place wall of markdown.
- **Recruiter-reaction framing** — each roast item follows a fixed ❌ problem / 🧠 why it hurts / 🔍 invisible cost structure, which forces specificity instead of generic "make it punchier" feedback.

## Try it

Open `linkedin_roast_rebuild.html` in any browser — no build step, no dependencies. Swap in your own profile text at the top of the flow to regenerate your own roast.

## Stack

Vanilla HTML/CSS/JS. No frameworks, no external libraries — same "single self-contained file" pattern I've used since Day 38.

## Next

Once this profile has one real project deliverable behind it, rerun the audit — the Experience score is capped until then by design.
