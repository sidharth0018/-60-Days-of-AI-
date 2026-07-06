# Day 36 — Cognitive Pattern Explorer 🧠

Part of the **#ABTalks 60-Day Claude AI Mastery Challenge** — one AI-assisted interactive app, every day, for 60 days.

## 🎯 What This Is

A single-file, offline-first web app that helps people explore their own thinking patterns through interactive scenarios — without ever diagnosing or clinically labeling anyone. It's built to feel like a calm, game-like self-reflection tool, not a psychological test.

**Live demo:** open `index.html` directly in any browser — no server, no build step, no internet required.

## 🧩 Core Features

| Feature | Description |
|---|---|
| Calm / Stress ambient modes | Two visual themes the user picks at the start, affecting color palette and pacing |
| Chapter 1 — Discover Your Thinking Style | 5 scenario-based multiple-choice questions, each option nudging a weighted score |
| Chapter 2 — Choose Your Priorities | Drag-and-drop ranking of 5 priority cards (mouse, touch, and keyboard supported) |
| Chapter 3 — Map Your Thinking | Drag-and-drop timeline — place unordered "thinking steps" into sequence slots |
| Final Reflection Journal | Animated percentage breakdown across 5 thinking styles + personalized reflective insight text |
| Progress indicator | Segmented progress bar tracks position across all 4 major steps |
| Accessibility | Full keyboard support (arrow keys, Enter/Space), ARIA roles, `prefers-reduced-motion` support + manual toggle |
| Responsive design | Works from mobile widths up through desktop |

## 🧠 The 5 Thinking Tendencies Modeled

1. **Analytical Thinker** — leads with logic and structure
2. **Emotional Intuitive** — leads with feeling and instinct
3. **Overthinking Loop Style** — revisits decisions repeatedly
4. **Action-First Decision Maker** — moves quickly, adjusts later
5. **Balanced Reflective Thinker** — blends reflection with timely action

Scores accumulate across all three chapters (scenario answers + drag-ranked priorities + drag-ordered timeline) into one running tally, then normalize to a percentage breakdown at the end.

## ⚠️ Important Design Principle: Non-Clinical by Default

This was a deliberate constraint I gave Claude from the start: **no diagnosis, no absolute labels, no clinical framing.** Every insight is phrased reflectively — "you often...", "this suggests..." — and the final screen carries an explicit disclaimer that this is an educational self-reflection tool, not a psychological assessment.

## 🛠️ Tech Stack

- Pure HTML + CSS + Vanilla JavaScript — **zero frameworks, zero dependencies**
- Single file (`index.html`) — fully portable, fully offline
- Native HTML5 Drag-and-Drop API, with a parallel touch-event fallback for mobile
- CSS custom properties for theming (Calm vs Stress mode swap via `data-mode` attribute)

## 📂 Files in This Folder

- `index.html` — the complete app (open directly in any browser)
- `LEARNINGS.md` — technical + prompt-engineering takeaways from building this
- `Day36.md` — full day summary for the 60-day challenge log

## 🔗 Challenge Links

- GitHub: [sidharth0018](https://github.com/sidharth0018)
- LinkedIn: [Sidharth Kumar](https://linkedin.com/in/sidharth-kumar-501768287)

---
*Built as part of Day 36/60 of the ABTalks Claude AI Mastery Challenge. Open to Data Analyst / Data Science opportunities.*
