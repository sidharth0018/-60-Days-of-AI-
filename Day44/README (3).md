# Day 44 — LinkedIn Roast & Rebuild Engine

Part of the [ABTalks 60-Day Claude AI Mastery Challenge](../README.md) — one AI-assisted build every day.

## Overview

A structured Claude prompt that turns "help me fix my LinkedIn" into a full audit-and-rebuild workflow: section-by-section scoring, an honest recruiter-style critique, a complete rewrite (headline, About, Experience, skills), a 7-day posting/outreach plan, and a shareable summary — all rendered as one interactive HTML report.

## Files in this folder

| File | Purpose |
|---|---|
| `Day44.md` | Full day summary — what was built, design decisions, why |
| `linkedin_roast_rebuild.html` | The interactive output report (open directly in a browser) |
| `LEARNINGS.md` | Prompt-engineering takeaways from building this |
| `prompt.md` | The full system prompt used to drive the roast-and-rebuild flow |

## Quick start

```bash
# No install needed — just open it
open linkedin_roast_rebuild.html
```

Or view it live by opening the file directly in any modern browser.

## Core idea

The prompt runs a fixed 5-part pipeline:

```
Input collection → Roast (scored critique) → Rebuild (rewrite) →
Before/After scorecard → 7-day activation plan → Shareable summary
```

Every rewritten section is generated **only** from what the user provides — the prompt explicitly bans inventing metrics, projects, or achievements. Where real evidence is missing, the output flags it as a gap to close rather than fabricating a number.

## Tech

Single-file HTML/CSS/JS. No build tools, no external dependencies, no frameworks — consistent with the "portable single-file app" pattern used across this challenge.
