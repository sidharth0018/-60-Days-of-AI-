# Day 48 — Compare & Decide Builder: Data Analyst Certification Comparator

**Part of the ABTalks 60-Day Claude AI Mastery Challenge**

## 🎯 What I Built

A single-file, interactive HTML web app that helps someone choose between competing
Data Analyst certification providers (Google, IBM, upGrad, DataCamp) using **real,
cited data** — not invented numbers.

The twist: the entire build process was driven by a structured **interview-first
prompt pattern**, where Claude asked me one multiple-choice question at a time
before generating a single line of code.

🔗 **Live app:** [`/app/index.html`](./app/index.html) — open directly in any browser, works fully offline.

## 🧩 The Problem

I'm evaluating which certification to invest in before I start applying for Data
Analyst / Data Science roles. Every "top 5 certifications" blog either:
- Recommends whatever the blog is monetizing, or
- Gives no real numbers (cost, duration) to actually compare with, or
- Mixes subjective claims ("great for beginners!") with hard facts, with no way
  to tell which is which.

I wanted a tool that separates **sourced facts** from **judgment calls**, and lets
*me* set the priorities instead of accepting someone else's ranking.

## 🛠️ How It Was Built

### 1. Interview-first prompting (MCQ-only)
Instead of describing the whole app in one prompt, I used a **"Compare & Decide
Builder"** meta-prompt that forced Claude to interview me first, one question at a
time, always as multiple choice:

1. What are you deciding between? → *Category, then 4 real example options*
2. Who is this for, and what's the one decision they need to walk away confident
   about?
3. What criteria matter? → *At least 4 measurable criteria*
4. Where should the data come from? → *Real, citable sources per criterion*
5. Fixed ranking or adjustable weights?

This turned a vague "build me a comparison tool" idea into a fully-specified brief
in five short exchanges — no wall of requirements to write myself.

### 2. Real research, not synthetic data
Claude ran multiple live web searches per provider (cost, duration, curriculum,
placement claims) and built a **sources panel** citing every claim — with anything
that couldn't be sourced (job-support quality, curriculum depth, recognition)
explicitly flagged as an **analyst estimate**, not a real number.

### 3. Weighted live ranking engine
- 5 criteria: Cost, Time to complete, Job/placement support, Curriculum depth,
  Industry recognition
- User-adjustable sliders normalize to 100% and recompute rankings in real time
- 3 presets: Balanced / Budget-first / Job-focused
- Cost and time are normalized against the most expensive/slowest option in the
  set, so the scoring scales automatically if more providers are added later

### 4. Collapsible transparency panels
- **"How this was researched"** — explains methodology and every data conflict
  Claude had to resolve (e.g. IBM's course count changed from 8 → 11 across
  sources; Google's monthly price varied $49 vs $59 across listings)
- **Sources panel** — every citation, linked, in one place

## 💡 Key Takeaways

1. **MCQ-gated interviews beat open-ended requirement gathering.** Answering
   "A, A, C, A, C" was faster and more precise than writing a spec myself — and
   it forced me to actually decide things (like weighting) I'd have left vague.
2. **Separating sourced fact from estimate is a trust feature, not a caveat.**
   Flagging "estimate" badges inline made the tool feel more credible, not less —
   because it's honest about what it doesn't know.
3. **Weighted scoring turns a listicle into a decision tool.** A static
   "Top 4 Certifications" ranking is someone else's priorities. Sliders let the
   ranking reflect *my* priorities (I care about placement support more than
   brand recognition, for example).
4. **Single-file HTML is still the fastest way to ship something someone can
   just open.** No build step, no dependency — copy the file, done.

## 🧱 Tech Stack
Vanilla HTML, CSS, JavaScript. No frameworks, no external libraries — fully
self-contained and works offline.

## 📁 Files in this folder
- `Day48.md` — this summary
- `README.md` — repo-level README section for Day 48
- `LEARNINGS.md` — deeper technical/prompt-engineering learnings
- `prompt.md` — the exact meta-prompt used to drive the build
- `app/index.html` — the working application

---
⬅️ [Day 47: Content Intelligence Studio](../day47) | [Day 49 →](../day49)
