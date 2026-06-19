# Day 19 — Football Intelligence Hub 🏆

Part of the [ABTalks 60-Day Claude AI Mastery Challenge](https://github.com/sidharth0018) — one reusable AI skill, built and documented every day.

## What This Skill Does

A multi-stage AI persona (**Football Intelligence Analyst + Sports Educator + Personality Assessor**) that turns a structured Excel workbook into a personalized, interactive intelligence report. It runs in 3 stages:

1. **Knowledge Calibration** — Asks the user's football familiarity level upfront and adapts terminology/depth for the rest of the session (no scoring yet).
2. **FIFA World Cup 2026 Prediction Report** — Analyzes historical performance (50-match base rates), current FIFA rankings, live form data, and in-progress 2026 group stage results to predict a winner, runner-up, and dark horse — each with a confidence score, supporting evidence, and risk factors.
3. **Football IQ Quiz** — A 5-question adaptive quiz (beginner → advanced) scored into a Football Awareness Score (0–100) with a fan classification (Beginner Fan → Football Expert).
4. **Messi vs. Ronaldo Personality Match** — A 15-question trait-based psychometric quiz (ambition, discipline, leadership, risk-taking, etc.) that calculates compatibility percentages with each legend, assigns one of 8 personality archetypes, and recommends a player/club/team/rivalry to explore.

All analysis is grounded in the data tables inside the source workbook — no hallucinated stats.

## Why This Skill Matters (Data Analytics Angle)

This isn't just a football quiz — it's a template for **data-driven personalization systems**:
- Multi-table relational reasoning (historical performance vs. live form vs. player-level stats)
- Confidence-scored predictive output (forces evidence + counter-evidence per prediction, not just a verdict)
- Psychometric scoring logic (weighted trait tallying → percentage compatibility → categorical archetype)
- Clean separation of **data layer** (Excel) → **logic layer** (prompt/skill) → **presentation layer** (interactive Q&A + exported report)

These are the same patterns used in recommendation engines, lead-scoring models, and BI dashboards — just themed around football.

## Files in This Folder

| File | Description |
|---|---|
| `README.md` | This file |
| `prompt-template.md` | The reusable system prompt for the Football Intelligence Hub skill |
| `sample-input/ABTalks_WorldCup_Intelligence_Master.xlsx` | Source data: team history, current form, live 2026 group stage results, player stats |
| `outputs/Football_Intelligence_Profile.docx` | Final generated report — predictions, IQ score, personality match, archetype, recommendations |

## Sample Output Snapshot

- **WC2026 Prediction:** Argentina (78% confidence) to win, Spain runner-up (65%), Morocco dark horse (55%)
- **Football IQ Score:** 96/100 — Football Expert tier
- **Personality Match:** 55% Ronaldo / 45% Messi → Archetype: **Relentless Competitor**

## Key Learnings (Day 19)

- Structuring a single prompt to run **sequential, stateful stages** (calibration → prediction → quiz → scoring → personality match) without losing context across the conversation
- Designing psychometric scoring logic that's transparent and explainable (each trait maps visibly to a legend's profile) rather than a black-box score
- Forcing every prediction to carry **both** supporting evidence and counter-evidence — avoids one-sided, overconfident outputs
- Exporting a structured conversational output into a polished, shareable `.docx` deliverable for portfolio use

## Tech Stack
`Claude (Sonnet)` · Excel data ingestion · Word document generation (docx)

---
🔗 Follow the full 60-day journey: [GitHub](https://github.com/sidharth0018) | LinkedIn
