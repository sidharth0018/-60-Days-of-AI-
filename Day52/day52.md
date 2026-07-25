# Day 52: FraudLens — System Design

**Challenge:** ABTalks 60-Day Claude AI Mastery Challenge
**Capstone:** Day 2 of 10 — System Design
**Date:** July 25, 2026

## Context

Continuing the FraudLens capstone with Claude acting as technical lead. Today's rule: read the PRD (from Day 1) as the source of truth, don't rethink the project, and produce a complete technical blueprint — no production code.

## Process Correction

The Day 1 Implementation Blueprint and Pitch Deck had been planned but never actually generated (Day 1 only produced the PRD). Rather than pretending they existed, this was flagged directly and resolved by backfilling the full Day 2–10 Implementation Blueprint before starting today's design work — keeping the daily log honest about what was actually built each day.

## Key Adaptation: No Traditional API

The standard system-design template assumes a frontend/backend split with REST endpoints. FraudLens is a self-contained Streamlit app with no separate client-server architecture, so this was explicitly adapted: `API.md` documents the **internal Python module interface** (function signatures between `app.py` and `src/` modules) instead of HTTP endpoints — the same design discipline, applied to the actual architecture rather than a generic assumption.

## Work Completed

1. **Tech stack finalized:** Streamlit (frontend + backend), no database, no auth, scikit-learn (Logistic Regression + Random Forest), imbalanced-learn (SMOTE), Streamlit Community Cloud hosting — all chosen for being free and matching a first-time-deployer skill level.
2. **System architecture:** Component diagram, data flow, and request lifecycle documented with Mermaid diagrams, separating the offline training pipeline from the runtime Streamlit app.
3. **Data schema:** Since there's no database, documented the dataset schema (`creditcard.csv` columns) and model artifact schema (`fraud_model.pkl`, `scaler.pkl`) instead — validated against every relevant PRD user story.
4. **API/module design:** Every function in `data_utils.py`, `model_utils.py`, and `explain_utils.py` specified with purpose, inputs, outputs, and error cases — before any of them are implemented.
5. **UI & user flow:** A deliberately flat, 2-screen app (Try It + Model Performance) with low-fidelity wireframes — no screen included without a clear reason.
6. **Project structure:** Full folder layout finalized, separating exploratory notebooks from production-ready `src/` code.
7. **Repository setup:** Cloned the dedicated `FraudLens` GitHub repo locally, initialized the folder structure, and set up `.gitignore` before any dataset download — preventing the large raw CSV from ever being accidentally committed.

## Key Decisions Locked In

| Decision | Choice | Reason |
|---|---|---|
| Repo strategy | Dedicated `FraudLens` repo, separate from the daily challenge repo | Recruiters click a product-named repo, not a Day-numbered folder |
| Database | None | No persistent user data in v1.0 scope; static model + dataset only |
| API style | Internal module interface, not REST | Matches the actual monolithic Streamlit architecture |
| UI screens | 2 (Try It, Model Performance) | Every screen justified against the PRD; no dashboard sprawl |

## Files in This Day
- `README.md` — day overview
- `Day52.md` — this file
- `LEARNINGS.md` — key takeaways
- `prompt.md` — reusable system design prompt
- `IMPLEMENTATION_BLUEPRINT.md`, `ARCHITECTURE.md`, `SCHEMA.md`, `API.md`, `UI-WIREFRAMES.md`, `PROJECT-STRUCTURE.md`

## Next Day
Day 53 (Capstone Day 3): Environment setup and exploratory data analysis — first hands-on code of the capstone.
