# Day 21/60 — Digital Footprint & Privacy Exposure Dashboard

> Part of the **60-Day Claude AI Mastery Challenge** — building one AI/data project a day, in public.

## 🎯 What I Built

An interactive, single-file HTML dashboard that analyzes a user's **digital footprint and privacy exposure** based on their self-reported app usage — styled like a premium cybersecurity / privacy-analytics tool (Stripe Dashboard × Apple Privacy Report × Google Privacy Checkup aesthetic).

Given a list of apps a person uses (Instagram, WhatsApp, YouTube, Google Pay, Amazon, etc.), the dashboard:

- Infers the **parent companies** behind each app
- Calculates a **Digital Footprint Score** and **Privacy Score** (0–100)
- Visualizes an **Exposure Heatmap** across all services
- Ranks companies by **estimated data exposure**
- Builds a **Data Collection Matrix** (identity, location, behavior, financial, social graph)
- Generates a **Risk Radar** of cross-app privacy risks
- Produces a speculative **Digital Twin Profile** (with explicit "Not enough information provided" where data doesn't support an inference)
- Surfaces the **Most Valuable Data Assets** from a data-broker's perspective
- Includes an interactive **Privacy Improvement Simulator**
- Closes with a **Final Verdict** summary

## 🧠 Why This Project

Most people have no real visibility into how their everyday app stack adds up to a profile that companies can build and monetize. The goal was to make that visible and *interactive*, while being strict about a core rule: **never present an inference as a fact.**

## 🔑 Key Design Rule: Facts vs. Estimates

This was the most important constraint of the build — every single output had to be labeled:

| Type | Example | Rule |
|------|---------|------|
| **Fact** | "15 apps reported," "Google has 4 services in this stack" | Directly stated by the user — no interpretation |
| **Estimate** | "Likely age bracket: teen/young adult," "Price-sensitive shopper" | Inferred from patterns — always labeled, never claimed as certain |
| **Insufficient data** | Mobility/travel profile | Explicitly shown as `"Not enough information provided"` instead of guessing |

No claims of accessing private/third-party databases anywhere in the tool — everything is inferred purely from the app names provided.

## 🛠️ Tech Stack

- Pure **HTML/CSS/JS** — single self-contained file, no build step, no dependencies
- CSS custom properties for a consistent dark dashboard theme
- Vanilla JS for the interactive Privacy Improvement Simulator
- Designed to be portable — opens directly in any browser

## 📊 Dashboard Sections

1. Digital Footprint Score (0–100, color-coded bands)
2. Privacy Score (0–100, color-coded bands)
3. Ecosystem Concentration breakdown by parent company
4. Exposure Heatmap (per-service risk intensity)
5. Company Exposure Ranking
6. Data Collection Matrix (✅ / ⚠️ / — per data category)
7. Risk Radar (severity-tagged risk list)
8. Digital Twin Profile (speculative, clearly labeled)
9. Most Valuable Data Assets (ranked by commercial value)
10. Privacy Improvement Simulator (click an action → see projected score change)
11. Final Verdict (Facts vs. Estimates summary)

## 💡 What I Learned

See [`LEARNINGS.md`](./LEARNINGS.md) for the full breakdown.

## 🚀 How to Use

1. Download `digital_footprint_dashboard.html`
2. Open it in any browser — no installation needed
3. Click through the Privacy Improvement Simulator buttons to see projected score changes

## 📁 Files

```
day21/
├── README.md                          ← this file
├── LEARNINGS.md                       ← key takeaways from building this
└── digital_footprint_dashboard.html   ← the working dashboard
```

---

**Challenge:** 60-Day Claude AI Mastery Challenge
**Day:** 21/60
**Connect:** [LinkedIn](#) · [GitHub](#)
