# Day 41 — Resume ATS Keyword Analyzer

**Challenge:** 60 Day Claude AI Challenge
**Day:** 41
**Category:** Job Search Tooling / Practical LLM Application

## What This Is
A Claude-powered CLI tool that compares a resume against a target job description and returns a structured ATS-style match report: matched keywords, missing keywords, a match score, and short, non-fabricated rewrite suggestions.

## Why I Built It
Applicant Tracking Systems commonly filter resumes on keyword overlap before a human reviewer ever sees them. As part of my own Data Analyst / Data Science job search, I wanted a reproducible way to check a resume against a job posting and quickly see what's missing — without hand-comparing bullet points every time.

## How It Works
1. **Extraction step** — Claude reads the job description and returns a strict JSON list of required skills, tools, and qualifications.
2. **Comparison step** — Claude compares that keyword list against the resume text and returns matched keywords, missing keywords, and up to 3 additive rewrite suggestions.
3. The script computes a simple match score (`matched / total keywords`) and prints a formatted report to the terminal.

## Tech Stack
- Python 3.10+
- `anthropic` Python SDK
- Claude Sonnet 5 (model string configurable via `--model`)
- Plain-text `.txt` inputs for resume and job description

## Key Design Decisions
- **Two-call architecture** (extract → compare) instead of one merged prompt — more accurate at a small latency cost.
- **Strict JSON-only output**, enforced via prompt instructions, with a fallback parser that strips markdown code fences if the model adds them anyway.
- **No hallucinated skills** — prompts explicitly forbid inventing experience the resume doesn't support.
- **CLI-first, single-purpose** — one resume vs. one job description, kept intentionally small to stay reproducible in under 30 minutes.

## Files in This Folder
- `README.md` — full write-up: objective, reproducible steps, troubleshooting, references
- `day41_notes.md` — raw prompts, response summaries, analysis, decisions, lessons learned
- `demo_script.py` — the runnable CLI tool
- `requirements.txt` — Python dependencies
- `LICENSE` — MIT license
- `CONTRIBUTING.md` — how to reproduce and contribute
- `.gitignore` — Python/editor/OS ignores
- `summary_card.md` — one-page profile-ready summary

## Result
Running the script on a sample resume/job description pair produced a 68% match score, correctly identifying 3 missing keywords (Tableau, A/B Testing, Stakeholder Reporting) and one actionable, non-fabricated rewrite suggestion.

## Next Steps
- Add PDF resume parsing (reuse Day 39's PDF Splitter/Merger logic).
- Batch mode: one resume against multiple job postings in a single run.
- Export match reports to Markdown/PDF.
