# Day 43 — AI Workflow Architect (Data Analyst Job Pipeline)

## 🎯 Objective
Build a self-contained AI Workflow Architect app that interviews the user (MCQ-first) about the workflow they want, then generates a complete, stage-by-stage, end-to-end execution plan — not generic advice. Applied it to my own use case: landing a Data Analyst / Data Science role at a fintech or consulting company in India.

## 🧩 What It Does
- Asks the user narrowing questions one at a time (industry → specific process → customization preference) before generating anything
- Outputs a single-page HTML app mapping the full pipeline from planning to execution
- Each stage includes: objectives, tasks, recommended AI tools + why, prompt examples, best practices, common mistakes, expected outputs, time estimates
- Interactive progress rail, per-stage checklists, sticky notes, dark mode, print view — all persisted via `localStorage`

## 🏗️ The Pipeline Generated (self-applied)
1. **Foundations** — SQL, Python/pandas, Power BI, core statistics
2. **Portfolio** — 3 credible projects, one fintech-themed, with business-first READMEs
3. **Resume & LinkedIn** — repositioning an ECE background as analyst-ready
4. **Job Search** — target list, tailored applications, warm outreach
5. **Interview Prep** — SQL drills, case studies, STAR stories
6. **Offer & Negotiation** — evaluating and closing

## 🛠️ Tech Stack
- Single-file HTML/CSS/JS — no frameworks, no external libraries
- `localStorage` for progress tracking, notes, and theme persistence
- CSS custom properties for light/dark theming
- Custom design system: ink/paper palette, Fraunces display type + Inter body + mono for data/prompts (deliberately avoided the generic cream/terracotta AI-design look)

## 💡 Key Design Decisions
- MCQ-first elicitation flow (via structured questions) instead of a single mega-prompt, so the output is scoped correctly before generation
- A horizontal "pipeline rail" as the signature UI element — reflects the literal concept of a career *pipeline*, not decoration
- Every stage ships copyable, ready-to-use AI prompts, not just tool names

## 📈 Outcome
A reusable meta-tool: same generator can produce a mapped workflow for any domain (marketing, HR, dev, etc.) by changing the interview answers — plus a personally useful, permanent artifact tracking my own job-search execution plan.

## ⏭️ Next Steps
- Day 44: (TBD)
- Possible extension: connect the checklist state to a real progress-sharing feature for the LinkedIn post series
