# Day 13/60 — Claude as a Career Intelligence & Job Search Engine

## What I Did Today
Used Claude end-to-end as a personal career analyst for Data Analyst / Business Analyst roles in India.  
Connected Claude to a **live job board (Indeed) via MCP** and ran a full career strategy session —  
profiling → job discovery → role scoring → skill gap analysis → market insights.

---

## Key Learnings

### 1. Structured Prompting = Consultant-Grade Output
When you give Claude a structured input (role + skills + goals + constraints + output format),  
it stops being a chatbot and starts behaving like a career consultant.

**Pattern learned:**

This is called a **context-rich directive prompt**.

---

### 2. Claude Can Use Real External Tools via MCP
Today Claude connected to **Indeed via MCP (Model Context Protocol)** — making live API calls  
to search real job listings across Bengaluru, Noida, Pune, Gurugram, Mumbai simultaneously.

**MCP = Claude + real-world apps (Indeed, Gmail, Google Drive, Slack, Asana...)**  
This is fundamentally different from Claude answering from training data.

---

### 3. Multi-Query Parallel Search Strategy
Instead of one broad search, Claude ran 7 targeted searches with different query strings:
- `"Data Analyst SQL Python fresher"` → Bengaluru  
- `"Business Analyst entry level product startup"` → Bengaluru  
- `"analyst trainee data 2026 batch"` → Hyderabad  
- `"Data Analyst junior SQL Power BI"` → Pune  

**Lesson:** Single searches miss roles because JD titles are inconsistent.  
Diverse query variations = better coverage.

---

### 4. AI as a Job Fit Scoring Engine
Claude scored each role 0–100 against my profile using:
- Skill match (does my stack align with JD?)
- Experience match (fresher-friendly?)
- Location fit
- Company type (product vs service vs MNC)
- Salary alignment

**Reusable prompt pattern:**

---

### 5. Market Intelligence — What Job Boards Don't Tell You
The most valuable insight wasn't a job listing — it was the **meta-analysis**:
- Razorpay, CRED, Groww, Zepto don't post on Indeed at all
- ₹8–12 LPA fresher roles live on LinkedIn, direct careers pages, and referrals
- Indeed only surfaces trainee programs and senior roles for freshers

**Lesson:** Ask Claude *"what does the pattern of these results tell me about the market?"*  
That meta-question produces strategic insight, not just a list.

---

### 6. Skill Gap Analysis as a Structured Roadmap

| Status | Skills |
|--------|--------|
| ✅ Have | SQL, Python/pandas, Power BI, Tableau basics |
| 🟡 Partial | Advanced SQL (CTEs, window functions), Advanced Excel |
| ❌ Gap | Statistics/A/B testing, Data storytelling, ETL basics, Portfolio project |

Converts "am I ready?" anxiety into a concrete action list.

---

### 7. Always Ask Claude to Visualise Comparative Data
Claude built 3 interactive dashboards today — career path map, job scoring table, skill demand chart.  
Claude defaults to text. For multi-variable comparisons, explicitly ask for a visual layout.

**Prompt pattern:**

---

## Top Jobs Found Today
| Role | Company | Location | Match |
|------|---------|----------|-------|
| Data Science / Analyst Trainee | Nucot | Bengaluru | 88/100 |
| Business Analyst Trainee | AUTOSherpa | Bengaluru | 75/100 |
| Data Analyst (Visualization CoE) | Bain & Company | Delhi | 62/100 |

---

## Big Picture Takeaway
Most people use AI to answer questions.  
Today I used it to **run a full career strategy session** in one conversation.

> Shift from *AI as search engine* → *AI as thinking partner*  
> The difference is how you structure the conversation: sequential, building context, each prompt informed by the last.

---

## Tools / Concepts Used
- MCP (Model Context Protocol) — live Indeed job search
- Context-rich directive prompting
- Multi-query parallel search strategy
- Contextual relevance scoring
- Structured skill gap analysis
- Claude interactive visualisations

---

*ABTalks 60-Day Claude AI Mastery Challenge*  
*Day 13 of 60 | 13 June 2026*
