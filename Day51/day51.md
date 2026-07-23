# Day 51: FraudLens — Product Discovery & Sprint Planning

**Challenge:** ABTalks 60-Day Claude AI Mastery Challenge
**Capstone:** Day 1 of 10 — Discovery & Requirements
**Date:** July 24, 2026

## Context

This day launches a 10-day capstone: a full mini software development lifecycle (Requirements → Design → Setup → Implementation → Testing → Deployment → Maintenance), run entirely as one continuing conversation with Claude acting as co-founder, product mentor, and technical lead.

The objective for Day 1 was explicitly **not** to write code or choose a tech stack — only to discover the right problem, define it clearly, and produce a complete requirements foundation for the remaining nine days.

## Process

Claude ran a structured, one-question-at-a-time discovery interview instead of asking for everything upfront. Each question was paired with a short explanation of *why* it was being asked, so the process stayed transparent rather than feeling like a generic form.

**Discovery flow:**
1. **Idea status** — confirmed no fixed idea; Claude was authorized to propose the project
2. **Time budget** — 2–4 hours/day for 10 days (capped scope to a focused, finishable build)
3. **What the project should prove** — applied ML/data science (prediction, classification, modeling), specifically to fill a gap not covered by existing resume projects
4. **Domain** — fintech/financial data, aligned with target companies (Razorpay, Groww, CRED)
5. **ML experience level** — beginner in hands-on ML despite strong DSA/theory background
6. **Deployment experience** — never deployed a Python backend before
7. **Specific problem** — credit card fraud detection (chosen over loan default prediction and spending-pattern anomaly detection)

Based on these constraints, Claude proposed hard guardrails before any build work began:
- Classical ML only (Logistic Regression, Random Forest) — no deep learning
- One clean, pre-processed public dataset (Kaggle Credit Card Fraud dataset)
- Streamlit for deployment — lowest-friction path from trained model to public demo
- A simple prediction interface, not a sprawling dashboard

## Outcome

**Project selected:** FraudLens — Credit Card Fraud Detection System

A one-paragraph project summary was presented for explicit approval before any deliverables were generated — preventing wasted work on a misaligned direction.

## Deliverable: Product Requirements Document (PRD)

A full professional PRD (`FraudLens_PRD.docx`) was generated, covering:
- Overview & problem statement
- Target users (recruiters, the builder, a simulated analyst persona)
- Goals and Day-10 success metrics
- Explicit in-scope vs. out-of-scope boundaries (v1.0 vs. Future Scope)
- Key features across data/modeling, application, and documentation
- High-level technical approach (detailed decisions deferred to the Implementation Blueprint)
- Risk register with mitigations
- Definition of Done for Day 10

## Key Decisions Locked In

| Decision | Choice | Reason |
|---|---|---|
| Problem type | Credit card fraud detection (imbalanced classification) | Directly interview-relevant for fintech DA/DS roles |
| Model complexity | Classical ML only | Matches beginner ML experience; avoids scope creep |
| Deployment target | Streamlit Community Cloud | Free, minimal config, first-time-deployer friendly |
| Explainability | Plain-English + feature importance (not full SHAP) | Achievable within time budget; SHAP deferred to Future Scope |

## Files in This Day
- `README.md` — day overview
- `Day51.md` — this file
- `LEARNINGS.md` — key takeaways
- `prompt.md` — reusable discovery/planning prompt
- `FraudLens_PRD.docx` — full PRD

## Next Day
Day 52 (Capstone Day 2): Design & Setup — turning the PRD into a concrete Implementation Blueprint covering Days 2–10, then beginning environment setup.
