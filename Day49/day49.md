# Day 49 — Personal AI Playbook (Prompt Builder + Loop Builder + Workflow Library)

## What I built
A single self-contained HTML app — a personal AI operating manual — that turns ad-hoc AI prompting into reusable, saved workflows. No backend, no build step, works offline once downloaded.

**Core features:**
- **Workflow Library** — 9 ready-made, fill-in-the-blank prompt templates across 4 categories tailored to my actual usage: Concept Learning, Project Building (EDA/dashboards/ML), Job Search & LinkedIn, DSA Practice
- **Prompt Builder** — assemble a custom prompt from 9 labeled building blocks (Role, Objective, Context, Constraints, Reasoning Strategy, Output Format, Tone, Examples, Quality Check) with a live text preview
- **Loop Builder** — wrap any prompt in Goal / Evaluation Criteria / Improvement Strategy / Stop Conditions / Safety Rules so an AI can self-check and iterate instead of one-shotting
- Local-storage persistence: favorites, custom workflows, theme — plus JSON export/import for backup
- Dark mode, keyboard shortcuts (`/` to search, `b` to jump to builder), onboarding modal, permanent "What is this?" help affordance

## Why this build
Day 47–48 built AI tools *for other people to use*. Day 49 turns the lens inward — every workflow in this app is templated from how *I* actually use AI day to day (explaining concepts I don't retain, EDA planning, resume rewriting, DSA hints).

## Process
1. Interviewed myself (via Claude, MCQ-first) on primary AI use case, biggest bottleneck, model preference, and experience level before writing a single line of code
2. Identified the real problem: not "I don't know how to prompt" but "I have no system to retain what I learn from AI explanations"
3. Designed 4 categories around that + adjacent repetitive tasks (project building, job search, DSA) instead of generic categories
4. Built block-based Prompt/Loop builders so the tool teaches reusable *systems*, not just static prompts
5. Every building block ships with an inline explanation — no jargon left undefined

## Tech
Single HTML file — vanilla JS, CSS custom properties for theming, `localStorage` for persistence, zero external JS dependencies (Google Fonts only).

## Try it
Open `app/index.html` directly in any browser — nothing to install.
