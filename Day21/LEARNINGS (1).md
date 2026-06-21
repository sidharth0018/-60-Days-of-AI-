# LEARNINGS — Day 21/60

## 1. Prompt design for "honest AI" outputs is harder than it looks

The hardest part of this build wasn't the HTML/CSS — it was designing a prompt structure that forced a clean separation between **Facts** (what the user actually told me) and **Estimates** (what could be plausibly inferred). It's easy for an AI-generated report to blur this line and present pattern-matching as certainty. Tagging every single claim with a `Fact` / `Estimate` badge — and explicitly using "Not enough information provided" when data was insufficient — made the output far more trustworthy and far more *defensible* as a piece of analysis.

**Takeaway for future projects:** any tool that makes inferences about a person (resume screeners, profile analyzers, recommendation engines) needs this same Fact/Estimate discipline baked into the design, not bolted on after.

## 2. A small, fixed dataset can still produce a rich, multi-layered dashboard

15 app names was the *entire* input. From that single list, the dashboard generated 9+ distinct analytical sections (scores, heatmaps, rankings, matrices, radars, simulators). This reinforced a core data-analytics skill: **a small structured input, modeled correctly, can support a lot of derived insight** — as long as every derived layer is clearly traceable back to the source data.

## 3. Building "premium SaaS" visual design takes deliberate constraints, not more code

To get a Stripe/Linear/Apple-Privacy-Report feel:
- Used a strict dark palette with CSS variables (`--bg`, `--panel`, `--border`, etc.) instead of ad-hoc colors
- Consistent border-radius, spacing, and typography scale across every card
- Color-coded severity system (🟢🟡🟠🔴) used *consistently* across every score, not just the headline numbers
- Avoided heavy JS frameworks — a single HTML file with embedded CSS/JS kept it portable and fast

**Takeaway:** visual polish in a dashboard comes more from *consistency of a small set of design tokens* than from adding more components.

## 4. Interactive simulators make abstract scores tangible

The Privacy Improvement Simulator (click an action → see a projected score change) turned a static report into something people actually want to interact with. This is a pattern worth reusing: whenever a project outputs a "score," consider adding a simple **what-if simulator** so the user can see the *lever*, not just the *number*.

## 5. Skill gap reinforced

This project didn't touch SQL/Power BI/pandas — a reminder that I still need to build a project where the *data itself* (not just a single hardcoded dataset) flows through a real ETL pipeline. That's a good candidate for an upcoming challenge day.

## Next Steps

- Day 22 candidate: rebuild this same concept but with a CSV upload + pandas backend to handle dynamic, larger datasets instead of a fixed list
- Continue applying the Facts vs. Estimates labeling discipline to any future "profile-building" or "scoring" project
