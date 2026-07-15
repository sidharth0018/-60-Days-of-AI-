# Day 45: AI Decision Strategist — Interactive Career Decision Report Generator

## 📌 Overview
Built an **impartial Decision Strategist prompt system** that interviews the user through 4 targeted questions, then auto-generates a fully interactive, animated HTML "Decision Report" — turning a messy internal debate into a data-backed verdict.

Used it live on a real decision: **"Go all-in on Data Analytics & AI vs. prep multiple career paths simultaneously."**

## 🎯 What It Does
- Runs a structured 4-question interview (one question at a time, no upfront analysis)
- Synthesizes answers into a single-file interactive HTML dashboard with:
  - **The Real Decision** — trade-off framing
  - **Case For Each Option** — strengths, hidden upside, weaknesses
  - **Assumption Buster** — surfaces cognitive biases (loss aversion, status-quo bias) at play
  - **Decision Matrix** — 7-dimension weighted scoring with animated bar charts
  - **Premortem** — imagines failure 12 months out, flags early warning signs
  - **7-Day Test Plan** — a low-cost real-world validation sprint
  - **Verdict** — a decisive, defensible recommendation
  - **Shareable Cards** — screenshot-ready summary cards for LinkedIn

## 🧠 Key Prompt Engineering Techniques
- **Turn-gated interviews**: forced one-question-at-a-time flow to avoid overwhelming the user and to keep free-tier usage efficient
- **Deferred synthesis**: explicitly instructed the model NOT to analyze until all inputs were collected — prevents premature, biased conclusions
- **Strict output constraints**: full CSS variable system, animation timing, and layout rules specified upfront so output is production-ready on the first pass, not iterated
- **Content-grounding rule**: "Use ONLY what the user said. Never invent facts" — kept the matrix scores tied to real answers instead of generic advice

## 🛠️ Tech Stack
- Single-file interactive HTML/CSS (no external JS frameworks)
- CSS `@keyframes` for animated score bars
- CSS variables for theming (dark mode, accent-coded sections)
- Fully responsive (mobile breakpoint at 600px)

## 💡 Key Learnings
1. Structuring an AI interview as strict turn-taking (vs. one big prompt) produces more honest, less rehearsed answers from the user.
2. Naming cognitive biases explicitly (sunk cost, loss aversion) makes the "Assumption Buster" section feel like real pushback, not generic advice — this is what separates a decision tool from a chatbot.
3. A weighted decision matrix with animated visuals turns a vague gut feeling into something shareable and defensible — useful both for personal clarity and as a portfolio artifact.
4. Constraining scope (exactly 4 questions, fixed sections, fixed CSS spec) made the output reliably high-quality in a single generation — no back-and-forth revisions needed.

## 🔗 Try It / Files
- `prompt.md` — the full Decision Strategist system prompt
- `decision_report.html` — sample generated output (real decision, not a demo)
- `README.md` — this file

---
📍 Day 45/60 — ABTalks 60-Day Claude AI Mastery Challenge
🔗 Connect: [LinkedIn](https://linkedin.com/in/sidharth-kumar-501768287) | [GitHub](https://github.com/sidharth0018)
