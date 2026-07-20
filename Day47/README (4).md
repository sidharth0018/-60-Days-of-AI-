# Day 46 — Content Intelligence Studio

**#60DayClaudeAIChallenge | ABTalks 60-Day Claude AI Mastery Challenge**

An AI content consultant that reviews LinkedIn/Instagram/YouTube content (text and/or images) through a panel of specialized AI reviewers — and hands back a full agency-style critique: scores, strengths, weaknesses, rewrites, alt hooks, a publishing checklist, and a before/after comparison. Every insight comes from live Claude API calls — nothing is hardcoded.

## 🎯 What it does

1. **Interviews the user first** — one MCQ question at a time (content type, platform, goal, upload type, review strictness) so the tool understands context before it touches the content.
2. **Assembles a custom reviewer pipeline** based on those answers — e.g. a job-seeker uploading a LinkedIn screenshot gets a Content Strategist, Visual Design Reviewer, Copywriting Analyst, Audience Psychologist, and a Recruiter/Hiring Lens instead of a generic growth-marketing reviewer.
3. **Calls Claude directly** for each reviewer with a dedicated system prompt, including sending the uploaded image as base64 so Claude analyzes the visual content itself.
4. **Synthesizes everything** through an "Editor-in-Chief" pass that combines all reviewer notes into one structured final report.
5. **Renders a premium SaaS-style dashboard**: animated score ring, category breakdown bars, tabbed reviewer panel, strengths/weaknesses/opportunities/recommendations, two rewritten captions + alt hooks, an interactive checklist, before/after comparison, executive summary, and an AI-estimated performance potential.

## 🧠 Why this build mattered

Most "AI content grader" demos either fake their output with hardcoded scoring logic or ask the model to return JSON — which breaks constantly with real LLM output (`Unexpected token`, `expected '{' or '('`, trailing commas, etc.). This build solves both problems:

- **Zero hardcoded logic.** Every score, strength, weakness, and rewrite is generated live by Claude. The app is a pipeline orchestrator, not an analysis engine.
- **Zero JSON parsing.** Instead of asking Claude for JSON, the synthesis prompt enforces a strict plain-text section format (`OVERALL_SCORE:`, `STRENGTHS:`, `REWRITE_1:`, etc.), and the frontend parses it with regex/line-splitting. This is far more resilient to the small formatting inconsistencies LLMs introduce and eliminates an entire class of runtime errors.

## 🛠️ Tech stack

- Single self-contained HTML file — vanilla HTML, CSS, and JavaScript only (no frameworks, no build step)
- Claude Messages API (`claude-sonnet-4-6`) called directly via `fetch`, including native image analysis (base64 image blocks)
- Custom plain-text response protocol (no JSON) parsed client-side
- CSS custom properties for full dark/light theming
- Animated SVG score ring, progress bars, and staged pipeline UI with a live activity log

## 📋 Reviewer panel (dynamically assembled)

| Reviewer | Role |
|---|---|
| 🧭 Content Strategist | Platform fit and goal alignment |
| 🎨 Visual Design Reviewer | Composition, typography, visual hierarchy (image uploads only) |
| ✍️ Copywriting Analyst | Hook strength, clarity, CTA effectiveness |
| 🧠 Audience Psychologist | First-2-seconds reaction, drop-off points, emotional triggers |
| 💼 Recruiter / Hiring Lens *(or 📈 Growth Analyst)* | Swaps automatically based on the user's stated goal |
| 🏆 Editor-in-Chief | Synthesizes all notes into the final structured report |

## 🚀 How to use

1. Open `content-intelligence-studio.html` in any modern browser (or as a Claude.ai artifact).
2. Answer the 5 quick MCQ questions.
3. Upload an image and/or paste caption text.
4. Watch the reviewer pipeline run live, then explore the full dashboard across six tabs: Reviewer Panel, Strengths & Gaps, Rewrites & Hooks, Publishing Checklist, Before vs After, and Final Report.

## 📂 Files in this folder

- `content-intelligence-studio.html` — the full working app
- `Day46.md` — day summary for the challenge log
- `LEARNINGS.md` — technical takeaways from this build
- `prompt.md` — the original prompt used to build this app

---
Part of the **[60-Day Claude AI Mastery Challenge](../README.md)** — one AI-assisted build a day, documented in public.
