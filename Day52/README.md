# Day 52 — FraudLens: System Design (Capstone Day 2/10)

Part of the **ABTalks 60-Day Claude AI Mastery Challenge**.

Second day of the FraudLens capstone. Today turned yesterday's PRD into a complete technical blueprint — architecture, data schema, module interfaces, UI flow, and folder structure — with zero production code written, per the capstone's SDLC-driven approach.

## 🎯 What This Day Covers
- Backfilled the Day 1 Implementation Blueprint (Days 2–10) since it wasn't generated on Day 1
- Full system architecture design, including a key adaptation: no traditional REST API since FraudLens is a self-contained Streamlit app
- Data schema design (dataset + model artifacts — no database needed for v1.0)
- Internal module interface design (`data_utils.py`, `model_utils.py`, `explain_utils.py`)
- UI wireframes and user flow for a 2-screen app (Try It + Model Performance)
- Final project folder structure
- Repository setup for the standalone `FraudLens` product repo

## 📦 Deliverables
| File | Description |
|---|---|
| `Day52.md` | Full day summary and outcomes |
| `LEARNINGS.md` | Key takeaways from today's system design process |
| `prompt.md` | The reusable system design prompt used to run this session |
| `IMPLEMENTATION_BLUEPRINT.md` | Full Day 2–10 build plan (backfilled + Day 2 executed) |
| `ARCHITECTURE.md` | Component diagram, data flow, request lifecycle (Mermaid) |
| `SCHEMA.md` | Dataset + model artifact schema |
| `API.md` | Internal module interface design |
| `UI-WIREFRAMES.md` | User flow + low-fidelity wireframes |
| `PROJECT-STRUCTURE.md` | Final repo folder structure |

## 🔗 Product Repo
Full FraudLens code and docs live in a dedicated repo: `github.com/sidharth0018/FraudLens`

## ➡️ What's Next
Day 53 (Capstone Day 3): Environment setup + exploratory data analysis on the Kaggle Credit Card Fraud dataset.
