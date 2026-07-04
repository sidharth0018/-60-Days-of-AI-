# Day 34/60 — Marketing Detective

**Challenge:** ABTalks 60-Day Claude AI Mastery Challenge
**Theme:** Turning a marketing-analytics case study into an interactive detective game
**Stack:** React 18 (CDN) + Babel Standalone, vanilla CSS, zero backend/API/DB

## The build

A single HTML file that runs a full "solve the marketing case" game:

- 12 fictional companies, each with complete campaign data: reach, CTR, engagement, conversions, sales, channel/budget split, customer comments, social performance, one root-cause mistake, 3 supporting clues, a full explanation, and suggested fixes.
- A random case loads every time the page is opened.
- Player progresses through 6 stages: **Case Assignment → Investigation Board → Deep Investigation → Accusation → Case Closed → Learning Report.**

## App flow (recap)

| Stage | What happens |
|---|---|
| 1. Case assignment | Dossier reveals company, industry, objective, audience |
| 2. Investigation board | Draggable evidence cards; 2 of 3 clues unlockable |
| 3. Deep investigation | 3rd, hidden clue behind a sealed folder |
| 4. Accusation | Pick the root cause from 4 options |
| 5. Case closed | Animated verdict stamp (correct/incorrect) |
| 6. Learning report | Full explanation, clues, quotes, fixes, animated budget chart |

## Design choices worth noting

- **Classic Noir theme** (black/white/red) — chosen to match a detective-bureau aesthetic rather than a generic dashboard look.
- Evidence gating (2 clues on the board, 1 clue locked behind a separate screen) creates the "aha" pacing instead of dumping all data at once.
- Accusation options mix 1 correct answer with 3 plausible-but-wrong distractors pulled from a rotating pool, so guessing isn't trivial.

## What this teaches (the actual marketing-analytics lesson underneath the game)

Each case is a small root-cause-analysis exercise: healthy top-of-funnel numbers (reach, CTR, engagement) paired with a broken bottom-of-funnel metric (conversion, retention, sales) — and the "detective work" is tracing that gap back to one specific operational or creative failure (broken landing page, missing frequency cap, bait pricing, mismatched ad-vs-product claims, etc.)

## Links

- Live file: `marketing-detective.html` (open directly in browser, no install)
- Full breakdown: see `README.md` and `LEARNINGS.md` in this folder

---
*Day 34 of 60 — building one AI-assisted interactive app per day.*
