# Learnings — Day 34: Marketing Detective

## 1. Constraint-driven prompting produces better architecture decisions

I explicitly asked for React + Babel via CDN, but with an instruction to fall back to vanilla JS if that choice would compromise standalone reliability. This forced an evaluation step before code generation instead of a default choice, and it's a pattern I want to reuse: state the preferred approach *and* the fallback condition, not just the preferred approach.

## 2. Game mechanics as a teaching device

The hardest design problem wasn't the code — it was pacing. If every clue is visible immediately, there's no "detective" feeling, just a data table. I solved this with staged reveals:
- 2 of 3 clues are click-to-reveal on the board (immediate friction, minimal)
- The 3rd clue is intentionally gated behind a separate "Deep Investigation" screen and a locked "Proceed" button, so the player can't skip to guessing without touching the evidence

This is a generalizable pattern for any future explainer/edu app: gate depth behind small interactions instead of a wall of text.

## 3. Multiple-choice generation needs guardrails, not just randomness

Early version of `buildOptions()` picked 3 random distractors from a pool with no relationship to the case. That's too easy — a distractor about "understaffed customer support" is obviously irrelevant next to a pricing-mismatch case. I kept the distractor pool broad on purpose (rotates across categories: pricing, staffing, targeting, competition) so the player actually has to compare it against the specific evidence gathered, not just eliminate the silliest-sounding option.

## 4. State management stayed simple on purpose

No Redux, no context providers — a single `stageIndex` integer in the root `App` component drives which of the 6 screens renders, plus a handful of `useState` hooks for clue-tracking and the selected accusation. For a linear, single-session flow like this, prop-drilling one level down is more readable than any state library would be. Lesson: match state tooling to actual complexity, not to "what's typically used."

## 5. Copyright-safe fictional data generation

All 12 companies, campaign stats, and customer quotes are invented — no real brand, real complaint, or real dataset was referenced or scraped. This matters both for going public with the repo and as a habit: any future "case study" style app I build should default to fictional data unless real data is explicitly sourced and cited.

## What I'd improve next iteration

- Persist score/streak across replays using `localStorage` (kept out of this version deliberately, since the brief required zero external persistence dependencies)
- Add difficulty tiers — some cases could hide the mistake behind more ambiguous metrics
- Track which of the 12 cases the player has already seen, to avoid repeats in a single session
- A results-history view so a user can review past verdicts across a session

## Relevance to my data analyst / data science goal

This project is really a compressed case-study generator: metrics tables, funnel breakdowns, budget allocation, and root-cause analysis — the same skeleton as an actual campaign post-mortem I'd be asked to produce as a data analyst. Framing my LinkedIn post around "diagnosing a funnel drop from CTR vs conversion divergence" rather than "I built a React game" is the more recruiter-relevant angle for Razorpay/Groww/CRED-style roles.
