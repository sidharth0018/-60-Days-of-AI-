# Day 29 — Learnings

## 🎯 The Prompt Engineering Challenge

This was the most structurally complex prompt I've written in the challenge so far — 8 distinct app states, each with its own data model, randomization logic, and scoring effect, all needing to feel like one coherent product rather than 8 disconnected screens.

What made this work wasn't a single mega-prompt. It was giving Claude:
1. A **fixed role stack** (frontend dev + UX designer + game designer + supply chain consultant) so every decision — copy, layout, and business logic — got evaluated from more than one lens at once
2. A **strict output constraint** (single HTML file, React CDN, no Tailwind/npm/backend) that forced clean, self-contained architecture instead of scattered dependencies
3. An explicit **beginner-empathy requirement** ("context before every decision," "why does this matter") — this one instruction shaped almost every screen, because it meant no option could just be a label; it needed a one-line business rationale attached

## 🧩 What I Learned About State Machines in React

This project is essentially an 8-state finite state machine (`welcome → company → crisis → warroom → negotiation → boardroom → ai → dashboard`) managed with nothing but `useState`. No routing library, no Context API, no external state manager.

Key lesson: for a linear, single-session flow like this, `useState` + conditional rendering is genuinely enough. Reaching for Redux or React Router here would have been over-engineering. Knowing *when not* to add complexity is as valuable a skill as knowing the tools that add it.

## 📊 Building a Composite Scoring Model

The final dashboard's Overall Crisis Score is a weighted formula:

```
Overall = Leadership(20%) + Negotiation(15%) + Resilience(20%)
        + CostControl(15%) + RiskManagement(15%) + Satisfaction(15%)
```

Each sub-score itself is derived from multiple raw inputs (War Room metric deltas, negotiation stats, boardroom answer scores, AI investment choices). This is functionally identical to how a real-world scorecard model works — a credit risk score, a vendor risk index, or an employee performance rating all follow this same "weighted roll-up of sub-metrics" pattern.

**This is the part of the project I'm most excited to reuse.** I want to rebuild this exact scoring logic as a Power BI dashboard using DAX measures — same weighted-KPI concept, different tool. That directly targets a gap I identified earlier in the challenge (Power BI / advanced Excel vs. what Data Analyst JDs expect).

## 🎨 UX Lesson: "Why This Matters" as a Design Primitive

Every single actionable choice in this app — War Room actions, AI investments, KPI cards — carries a short italicized "why it matters" line. This wasn't a cosmetic add-on; it was baked into the data structure itself (`why` and `impact` fields sit next to every option object).

Lesson: if you want an app to *teach* while someone plays it, the explanation can't be bolted onto the UI afterward — it has to live inside the data model from the start.

## 🔧 What I'd Improve With More Time

- Add a **branching consequence system** so War Room choices affect which negotiation dialogue options appear (right now the stages are sequential but independent)
- Persist scores across multiple playthroughs (e.g., using `localStorage`) to let users track improvement — currently intentionally excluded per the "no browser storage" constraint for artifact portability, but a real deployed version would benefit from it
- Add a **difficulty/industry filter** so a user could specifically practice, say, pharma supply chain crises vs. apparel ones
- Build the **Power BI companion dashboard** mentioned above, treating this app's random playthroughs as a synthetic dataset

## 💼 Why This Matters for My Data Analyst / Data Science Job Search

This project sits at the intersection of three things I want to demonstrate to recruiters at product companies:

- **Business logic translation** — turning vague real-world tradeoffs (cost vs. speed vs. trust) into an explicit, weighted, quantifiable model
- **Domain fluency** — supply chain / operations context, which shows up frequently in analyst JDs, especially at companies with physical logistics or e-commerce operations
- **Communicating data clearly to non-technical stakeholders** — the entire UX philosophy of this app (explain before you ask someone to decide) is exactly the skill an analyst needs when presenting a dashboard or insight to a business team that doesn't think in SQL

---

**#Day29 #60DayClaudeChallenge #SupplyChain #DataAnalyst #ReactJS #AIBuilding**
