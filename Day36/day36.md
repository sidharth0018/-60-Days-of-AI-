# Day 36/60 — Cognitive Pattern Explorer

**Challenge:** #ABTalks 60-Day Claude AI Mastery Challenge
**Domain:** Psychology-inspired self-reflection / UX interaction design
**Stack:** HTML + CSS + Vanilla JS (single file, fully offline)

## 🎯 Goal of the Day

Build an interactive, game-like self-reflection app that helps someone explore their own thinking patterns — analytical, emotional, overthinking, action-first, or balanced — without ever slipping into clinical or diagnostic language.

## 🏗️ What I Built

**Cognitive Pattern Explorer** — a 4-step guided experience:

1. **Start Screen** — pick a Calm or Stress ambient mode
2. **Chapter 1 — Discover Your Thinking Style** — 5 scenario-based multiple choice questions
3. **Chapter 2 — Choose Your Priorities** — drag-and-drop ranking of decision-making priorities
4. **Chapter 3 — Map Your Thinking** — drag-and-drop timeline sequencing of thought-process steps
5. **Final Reflection Journal** — animated percentage breakdown across 5 thinking styles, with personalized reflective insights (not diagnoses)

## 🔑 Key Technical Decisions

- **Single-file, zero-dependency architecture** — everything (HTML/CSS/JS) lives in one `index.html` so it works completely offline, which matters for a self-reflection tool people might want to keep private and local.
- **Dual drag-and-drop input handling** — native HTML5 DnD for desktop, parallel touch-event listeners for mobile, plus a fully independent keyboard-only path (arrow keys + on-card buttons) for accessibility.
- **Unified scoring model** — every interaction across all 3 chapters (answers, rankings, timeline order) feeds one shared `addScore()` function into a single 5-category score object, normalized into percentages at the end.
- **Reflective, non-clinical language throughout** — a hard constraint from the very first prompt: no absolute labels, no diagnosis, phrasing like "you often...", "this suggests..." — reinforced with an explicit disclaimer on the results screen.

## 💡 Why This Matters for My Data Analyst Journey

This day's build reinforced core data-thinking skills that translate directly to analyst work:
- Weighted scoring and normalization logic (score/total × 100)
- Turning qualitative interactions (choices, rankings, sequencing) into structured, aggregatable data
- Designing a clear breakdown visualization (percentage bars) from raw counts — the same conceptual step as building a distribution chart in Power BI or Excel

## 🔗 Links

- Code: this folder (`index.html`)
- GitHub: [sidharth0018](https://github.com/sidharth0018)
- LinkedIn: [Sidharth Kumar](https://linkedin.com/in/sidharth-kumar-501768287)

## 📌 Status

✅ Day 36 complete — 24 days remaining in the #ABTalks 60-Day Claude AI Mastery Challenge.
Actively building toward Data Analyst / Data Science roles (targets: Razorpay, Groww, CRED, Deloitte, Genpact) — open to opportunities.

#60DayClaudeChallenge #BuildInPublic #ClaudeAI #DataAnalyst #OpenToWork
