# Day 35: Prompt Puzzle — Master AI Prompting Through Play

**Challenge Day:** 35 / 60
**Domain Focus:** Data Analysis / Data Science (Intermediate difficulty scenarios)
**Build Type:** Single-file HTML/CSS/vanilla JS interactive game
**Time Spent:** ~[1392sec]

## 🎯 Goal
Build an offline, single-file HTML application that teaches prompt engineering through gamified challenges, specifically using Data Analyst / Data Science scenarios (data cleaning, EDA, SQL, model explanation, KPI design, A/B testing) — both to sharpen my own prompting skills and to have a portfolio piece that shows applied product thinking.

## 🛠️ What I Built
- 6 randomized scenarios covering: sales data cleaning, EDA summaries, SQL query generation, predictive model explanation, dashboard KPI definition, and A/B test interpretation
- 3 challenge types: Build the Prompt (drag-and-drop), Clean the Prompt (strip over-engineered prompts), Choose the Best Prompt (multiple choice)
- Live scoring engine: accuracy, time, moves, wrong placements, hints used, optimization bonus
- Full "Prompt Performance Report" screen: score, rating, rank, Prompt DNA radar-style tags, personalized feedback, next milestone, and a final optimized prompt example
- Premium dark UI with gradient accents, floating toast notifications, hover/drag micro-interactions, and animated progress bar

## 🐛 Bug I Hit & Fixed
Ran into a blank white page after first generation — turned out to be a single incorrectly escaped apostrophe inside a JS string that broke the whole `<script>` block. Diagnosed it by extracting the JS with a Python regex and running `node --check` on it, found the exact line/character, and fixed it by switching to double-quoted strings. Full details in `LEARNINGS.md`.

## 💡 Key Prompt Engineering Principles Reinforced
- **Specificity + Context** beats vague asks (naming exact columns/tables changes everything)
- **Role framing** calibrates tone and depth ("act as a senior data analyst" vs no role)
- **Audience framing** determines jargon level and length
- **Output format requests** (numbered lists, word limits, code w/ comments) make output immediately usable
- **Decision-oriented prompting** (ask for a recommendation, not just analysis) drives action

## 🔗 Links
- Live file: `prompt-puzzle.html` (open directly in any browser, works fully offline)
- Part of: [60-Day Claude AI Mastery Challenge](https://github.com/sidharth0018) by Sidh

## ⏭️ Next Steps
- Consider adding a Power BI/Tableau-specific scenario set (direct skill-gap practice)
- Possibly extract the scenario-authoring pattern into a reusable "scenario builder" skill for future challenge days
