# Day 27 — Prior Authorization Story Simulator

**60-Day Claude AI Mastery Challenge | ABTalks**

A narrative, choice-driven chat simulation that walks through a Prior Authorization journey scene-by-scene — built as a single self-contained HTML file using Tailwind CSS (CDN) and vanilla JavaScript.

🔗 **Live demo:** open `pa_story_simulator.html` directly in any browser (no server, no install).

---

## 🎯 What this project does

This is a follow-up to Day 26's drag-and-drop PA workflow simulator — same domain, different format. Instead of moving a case card across lanes, the user reads (and steers) a chat-style story following **Rahul**, a patient newly diagnosed with Rheumatoid Arthritis, and **Priya**, a healthcare operations specialist who explains what's happening at each step.

The story runs across **8 scenes**, each ending in 2 choices that branch the dialogue before the story continues:

1. Doctor Visit — diagnosis and prescription
2. Insurance Roadblock — PA submitted directly to the payer, no pharmacy involved
3. What is PA? — plain-language explanation, including why step therapy isn't just bureaucracy
4. Insurance Review — the 4 things a payer actually checks (eligibility, documentation, ICD-10 match, step therapy history)
5. Denial — missing documentation, and why a denial isn't permanent
6. Appeal — assembling a Letter of Medical Necessity and filing
7. Approval — reference number issued, PA saved on file
8. Takeaways — split into a Patient perspective and a System perspective (denial rate, appeal rate, resolution time)

"StarCare Health" is used throughout as a clearly labeled **illustrative example** payer, not a real insurer.

## 🧩 Key features

- **Append-only chat feed** — every message is built with `document.createElement` + `appendChild`. The chat container's `innerHTML` is never reassigned, even on restart (cleared via `removeChild` in a loop instead)
- **Two distinct chat personas** — Rahul (left, blue bubbles) and Priya (right, indigo bubbles), each with their own avatar
- **Narrator / doctor lines** render as centered italic text only — never as chat bubbles, keeping narration visually distinct from dialogue
- **Branching choices** after every scene — two options that change the dialogue that follows before the story moves on
- **Typing indicator animation** before each bubble for natural pacing, instead of dumping all text at once
- **Progress bar + scene counter** across the top, tracking position across all 8 scenes
- **Cited, real-world grounded content** — AMA 2023 PA Survey delay statistic and a physician-office resolution-time stat are surfaced as highlighted info cards at the relevant moments
- **Beginner-friendly language** throughout — no insurance jargon left unexplained

## 🛠️ Tech stack

- **HTML + Tailwind CSS (via CDN) + Vanilla JavaScript**
- No frameworks, no build step, no localStorage
- Single file: `pa_story_simulator.html` — fully portable, runs offline (Tailwind CDN requires an initial internet connection to load)

## 🤖 How Claude was used

1. Gave Claude a tightly detailed spec: exact characters, their screen positions, a hard rule that narrator/doctor text must never appear as a chat bubble, and a strict technical constraint to only use `createElement`/`appendChild` and never touch `innerHTML` on the chat container
2. Asked for all 8 scenes with specific factual content baked in per scene (e.g. the AMA 2023 citation, the "no pharmacy involved" PA flow, the staff-hours cost of a denial) plus 2 branching choices after every scene
3. Claude produced the full single-file app in one pass, including a typing-indicator animation and a restart flow that respects the append-only constraint by using `removeChild` instead of clearing `innerHTML`
4. This built directly on the design system and lane-based domain knowledge established in Day 26, applied to a narrative format instead of a board-game format

See `LEARNINGS.md` for the detailed breakdown.

## 📂 Files in this folder

| File | Description |
|---|---|
| `pa_story_simulator.html` | The complete, runnable story simulator (open directly in a browser) |
| `README.md` | This file |
| `LEARNINGS.md` | Day 27 reflections — prompting approach and key takeaways |

## 🚀 How to run

1. Download `pa_story_simulator.html`
2. Open it in any modern browser (needs internet access once, to load the Tailwind CDN script)
3. Read through the story and pick a choice at the end of each scene

---

**Part of my [60-Day Claude AI Mastery Challenge](https://github.com/sidharth0018) — one AI-assisted build, every day, fully documented.**
