# Day 52 — Learnings

## 1. Don't let a template force a wrong architecture
The standard system-design process assumes frontend/backend/database/API/auth. Blindly filling in all five would have invented a database and REST API that this project doesn't need. The right move was adapting the template to the actual architecture (Streamlit monolith) and explaining why — not forcing the project to fit the template.

## 2. Catching a missing deliverable early beats pretending it exists
When Day 2 assumed a Blueprint that was never actually generated on Day 1, the honest fix was to flag it and backfill it properly — not silently invent Day 2 content "as if" a blueprint existed. This kept the whole capstone's documentation trail accurate.

## 3. A dedicated product repo matters for recruiter visibility
Nesting FraudLens inside the daily challenge repo would bury it. A standalone repo means a clean, direct link on a resume or LinkedIn profile — the daily challenge repo becomes a build log that points to it, not a container for it.

## 4. `.gitignore` has to exist before the risky file does
Setting up `.gitignore` to exclude the raw dataset *before* downloading it (rather than after) removes the entire class of "oops, committed a 150MB CSV" mistakes that are common in ML project repos.

## 5. Documenting the "why," not just the "what," makes docs reusable
Every design doc today (architecture, schema, API) explains *why* a decision was made, not just what was decided. That makes these docs genuinely useful on Day 5 or Day 7 when implementation questions come up — not just a one-time planning artifact.
