# Day 43 — AI Workflow Architect
### Data Analyst Job Pipeline Generator

Part of the [60-Day Claude AI Mastery Challenge](../README.md) — one AI-assisted application built and shipped every day.

---

## 📌 Overview

**AI Workflow Architect** is a meta-tool: instead of generating generic advice, it interviews the user first (MCQ-style, one question at a time) to narrow down exactly what workflow they need mapped, then generates a complete, end-to-end, stage-by-stage execution plan as a self-contained interactive web app.

For Day 43, I applied it to my own real use case: **landing a Data Analyst / Data Science role at a fintech or consulting company in India** — producing a 6-stage pipeline from skill-building to offer negotiation.

🔗 **Live demo:** *(add your hosted link / GitHub Pages link here)*
📂 **File:** [`ai-workflow-architect-data-analyst.html`](./ai-workflow-architect-data-analyst.html)

---

## 🎯 Problem It Solves

Most AI tools answer "how do I get a data analyst job?" with a flat checklist or a wall of generic advice. This tool instead:
- Scopes the request properly before generating anything (industry → specific process → output format)
- Breaks the goal into ordered, dependent stages (skills feed portfolio, portfolio feeds resume, resume feeds outreach, etc.)
- Gives each stage the depth of a mini-playbook: tasks, tools, prompts, mistakes, and success criteria — not just bullet points

---

## ✨ Features

| Feature | Description |
|---|---|
| **Guided elicitation** | MCQ-first flow narrows the ask before any generation happens |
| **6-stage pipeline** | Foundations → Portfolio → Resume/LinkedIn → Job Search → Interview Prep → Offer & Negotiation |
| **Interactive progress rail** | Visual pipeline tracker showing overall completion % |
| **Per-stage checklists** | Click-to-complete tasks, persisted across sessions |
| **Copyable AI prompts** | Ready-to-use prompts for each stage, one-click copy |
| **Sticky notes per stage** | Freeform notes saved locally per stage |
| **Dark mode** | Full theme toggle, persisted |
| **Print view** | Clean, distraction-free printable version of the whole guide |
| **Zero dependencies** | Single HTML file — no frameworks, no build step, no external libraries |

---

## 🏗️ The Pipeline (Self-Applied Example)

1. **Foundations** (3–4 wks) — SQL, Python/pandas, Power BI, core statistics
2. **Portfolio** (3–4 wks) — 3 credible projects, one fintech-themed, business-first READMEs
3. **Resume & LinkedIn** (1–2 wks) — repositioning an ECE background as analyst-ready
4. **Job Search** (ongoing) — target company list, tailored applications, warm outreach
5. **Interview Prep** (2–3 wks) — SQL drills, case studies, STAR stories
6. **Offer & Negotiation** (~1 wk) — evaluating offers beyond CTC, closing

Each stage includes: objectives, tasks, recommended AI tools + rationale, prompt examples, best practices, common mistakes, expected output, and time estimate.

---

## 🛠️ Tech Stack

- **HTML/CSS/JS** — vanilla, single file, no frameworks
- **`localStorage`** — persists progress, notes, and theme preference client-side
- **CSS custom properties** — drives the full light/dark theme system
- **Data-driven rendering** — all stage content lives in a single JS array and is rendered dynamically, avoiding repetitive hardcoded HTML

---

## 🎨 Design Notes

Deliberately avoided the common "AI-generated" visual defaults (cream background + terracotta accent, or near-black + neon accent). Instead:

- **Palette:** ink/paper base tones with a warm amber (`#d97b2c`) and muted teal (`#3f7d6b`) accent pair
- **Type:** Fraunces (display) + Inter (body) + monospace (data/prompts/labels) — three distinct roles instead of one neutral font
- **Signature element:** a horizontal "pipeline rail" with stage nodes — chosen because the content literally *is* a pipeline, not as decoration

---

## 🚀 How to Use

1. Open the HTML file in any browser — no installation needed
2. Click through the stage tabs or the progress rail to navigate
3. Check off tasks as you complete them — progress saves automatically
4. Copy any prompt directly into Claude/ChatGPT for that stage's tasks
5. Use the notes box per stage to jot reminders or links
6. Toggle dark mode or print the guide anytime

---

## 💡 Key Learnings

- Structuring generation around explicit, sequential MCQ elicitation produces far more scoped output than a single freeform prompt
- A static HTML file with `localStorage` can feel like a genuinely stateful app with zero backend
- Treating a career plan as an interactive, reusable artifact (not a one-time chat response) makes it something to actually return to

---

## 📅 Challenge Context

**Day 43 of 60** — [ABTalks 60-Day Claude AI Mastery Challenge](../README.md)
Building one AI-assisted application every day and documenting the process publicly.

- 📄 [Day43.md — full day summary](./Day43.md)
- 📄 [LEARNINGS.md — challenge-wide learnings log](../LEARNINGS.md)
- 💼 Connect: [LinkedIn](https://linkedin.com/in/sidharth-kumar-501768287)
- 💻 More builds: [GitHub Profile](https://github.com/sidharth0018)
