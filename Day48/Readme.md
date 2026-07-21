# Day 48 — Compare & Decide Builder 🎓⚖️

> Part of the [ABTalks 60-Day Claude AI Mastery Challenge](../README.md)

## Overview
An interactive, single-file web app that compares Data Analyst certification
providers (Google, IBM, upGrad, DataCamp) on **cost, time, job support,
curriculum depth, and industry recognition** — with adjustable priority weights
and a live-updating ranked result.

Every hard number is sourced and cited. Every judgment call is flagged as an
estimate. Nothing is invented.

## Why This Build Matters
Most "which course should I take" content is either an ad in disguise or a
listicle with no real numbers. This app treats the decision the way a research
analyst would: gather real data, cite it, separate fact from judgment, and let
the *user* set the priorities instead of imposing one.

## How to Use
1. Open `app/index.html` in any browser (no install, no server needed)
2. Adjust the 5 priority sliders on the left, or pick a preset
   (Balanced / Budget-first / Job-focused)
3. Watch the ranked cards update live
4. Expand "How this was researched" and "Sources panel" for full transparency

## Build Process
Built using a structured **MCQ-only interview prompt** ("Compare & Decide
Builder") that made Claude ask clarifying questions one at a time before writing
any code — see [`prompt.md`](./prompt.md) for the exact meta-prompt used.

## Tech Stack
- HTML5 / CSS3 / Vanilla JavaScript
- No frameworks, no external libraries, no build step
- Fully responsive, works offline

## Files
| File | Purpose |
|---|---|
| `Day48.md` | Full day summary and learnings |
| `README.md` | This file |
| `LEARNINGS.md` | Deeper prompt-engineering and technical notes |
| `prompt.md` | Exact meta-prompt used to drive the build |
| `app/index.html` | The working application |

## Live Demo
Open [`app/index.html`](./app/index.html) directly — works fully offline, no
setup required.

---
🔗 Connect: [LinkedIn](https://linkedin.com/in/sidharth-kumar-501768287) · [GitHub](https://github.com/sidharth0018)
