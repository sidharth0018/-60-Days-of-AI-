# Day 16 — Stock Fundamental Research with Claude AI 📊

> **ABTalks 60-Day Claude AI Mastery Challenge**
> *Building real skills with AI, one day at a time.*

---

## 🎯 What I built today

A **Stock Fundamental Research Analyst** powered by Claude AI — capable of pulling live market data, running side-by-side company comparisons, and generating investor-grade research reports using structured prompting and the `/stock-fundamental-research` skill.

Today's test case: **Reliance Industries vs HDFC Bank** — a deep Compare mode report.

---

## 🔍 What this skill does

| Mode | What it generates |
|------|------------------|
| **Quick Take** | 150–220 word snapshot with CMP, P/E, ROE, ROCE, growth trend, strengths & watch-points |
| **Deep Dive** | Full tabbed HTML report: Snapshot, Valuation, Growth, Health, Returns, Peers, Ownership |
| **Compare** | Side-by-side metrics, charts, "Where A leads / Where B leads" verdict |
| **Pros & Cons** | 3–5 evidence-backed strengths and risks |
| **Portfolio Fit** | Concentration analysis, sector overlap, what a stock adds or duplicates |

---

## 📈 Today's output: Reliance vs HDFC Bank

### Key metrics compared (FY25 data)

| Metric | Reliance Industries | HDFC Bank |
|--------|-------------------|-----------|
| CMP | ₹1,331 | ₹1,935 |
| Market Cap | ₹17.7L Cr | ₹11.97L Cr |
| Revenue (FY25) | ₹9.65L Cr | ₹2.73L Cr |
| Net Profit | ₹69,648 Cr | ₹70,792 Cr |
| P/E (TTM) | ~24x | ~19x |
| P/B | 2.0x | 2.8x |
| ROE (3Y avg) | 8.77% ⚠️ | ~13% ✅ |
| ROCE | 9.18% | ~12% |
| Gross NPA | N/A | 1.33% ✅ |
| Promoter Holding | 50% | 0% (no promoter) |
| Dividend Yield | 0.4% | 1.1% |
| 1Y Return | ▼ 9.1% | ▼ 7.4% |

---

## 💡 Key insights from the report

### Where Reliance leads
- Sheer revenue scale (₹9.65L Cr — India's largest company by revenue)
- Strong promoter conviction — 50% promoter holding, zero pledging
- Diversified across 5 verticals: O2C, Jio, Retail, New Energy, Media
- New growth catalyst: Meta AI Data Center JV in Jamnagar (168 MW)
- Long-cycle capex bets positioning it for the next decade

### Where HDFC Bank leads
- Higher return quality — ROE ~13% vs RIL's 8.77%
- Better dividend yield (1.1% vs 0.4%)
- Pristine asset quality — Gross NPA 1.33%, Net NPA 0.43%
- Cheaper valuation on P/E basis (~19x)
- Commands 37% of private sector banking advances

### Watch-points
- **RIL**: ROE below 10%, profit growth slowing to 2.4% YoY, heavy capex cycle compressing FCF
- **HDFC Bank**: NIM under pressure (dipped to 3.35% in Q1FY26), operating profit declined 9.4% YoY in Q4FY25

---

## 🛠️ How I prompted Claude

```
/stock-fundamental-research

Test the skill using Reliance and HDFC Bank.
Generate a compare report.
```

That's it. One command. Claude:
1. Ran **4 live web searches** across Screener, Tickertape, Business Standard, TipRanks, and NSE filings
2. Cross-verified key figures across at least 2 sources (per skill rules)
3. Generated an **interactive HTML dashboard** with 4 live Chart.js visualizations
4. Applied the research checklist: CMP, Market Cap, P/E, P/B, ROE, ROCE, NPA, NIM, promoter holding, FII/DII, moat, dividends, and 1Y/5Y returns
5. Delivered a balanced verdict — no winner declared, no buy/sell recommendation

---

## 🧠 What I learned today

### 1. Skill files = reusable expertise
The `/stock-fundamental-research` skill acts like a saved expert persona. Instead of reprompting Claude each time with all the rules, the skill encodes:
- Source priority (Screener → Tickertape → Moneycontrol → NSE)
- Research checklist (20+ metrics)
- Interpretation rules (what counts as "good" ROE, D/E, FCF)
- Output format (Quick Take / Deep Dive / Compare)
- Mandatory rules (never fabricate, always cite, never give buy/sell calls)

**Lesson**: Custom skills in Claude are like SOPs for AI — you define the process once and reuse it.

### 2. Structured output from unstructured data
Claude pulled data from 8+ different sources with inconsistent formatting and normalized it into a clean comparison table + 4 interactive charts. This is the core value proposition of AI in data analytics — transforming noisy inputs into structured, comparable outputs.

### 3. Research discipline built into the prompt
The skill forces Claude to:
- Flag unavailable data rather than hallucinate
- Cite sources next to every key figure
- Use consistent interpretation thresholds (ROE >15% = good, <10% = weak)
- End with a disclaimer

This is what separates a **research-grade output** from a casual AI answer.

### 4. The "Compare" mode is the most powerful
Side-by-side comparisons force clarity. When you put two stocks next to each other on the same 20 metrics, patterns emerge that a standalone analysis misses — like how HDFC Bank's net profit is nearly identical to RIL's despite having 1/3rd the revenue.

---

## 📊 Visualization breakdown

The interactive dashboard included:

- **Net Profit bar chart** — RIL (₹69,648 Cr) vs HDFC Bank (₹70,792 Cr)
- **ROE & ROCE grouped bars** — Returns quality gap clearly visible
- **P/E & P/B valuation comparison** — HDFC cheaper on P/E, pricier on P/B
- **Shareholding pattern** — Promoter / FII / DII / Public breakdown for both

All charts built with Chart.js, color-coded by company, with proper ARIA labels for accessibility.

---

## 🔗 Tools & stack

| Tool | Role |
|------|------|
| Claude Sonnet 4.6 | AI reasoning, data synthesis, report generation |
| Web Search (4 queries) | Live market data from Screener, Tickertape, BSE filings |
| Chart.js | Interactive visualizations |
| Custom Skill File | Research rules, checklist, output format |
| HTML/CSS artifact | Full interactive dashboard rendered inline |

---

## 📁 Files in this folder

```
day16-stock-research/
├── README.md              ← This file (learning log + report summary)
└── research-report.html   ← Standalone interactive compare dashboard
```

---

## ⚠️ Disclaimer

> All content in this report is for **educational purposes only**.  
> It is **not investment advice** and not a buy/sell/hold recommendation.  
> Verify all figures independently at Screener.in, NSE, or BSE before making any financial decision.  
> **The final decision is always yours.**

---

## 🔖 Challenge progress

| Day | Topic |
|-----|-------|
| Day 1–10 | Prompt engineering, role-based prompting, Claude model selection |
| Day 11–15 | Resume optimization, personal branding, portfolio website, LinkedIn strategy |
| **Day 16** | **Stock Fundamental Research — Reliance vs HDFC Bank Compare Report** |

---

*Follow along: [GitHub — sidharth0018](https://github.com/sidharth0018) · LinkedIn: ABTalks*

> *"The best way to learn AI is to build with it every single day."*
