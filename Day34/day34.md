# Day 34 — Marketing Detective

Part of the [ABTalks 60-Day Claude AI Mastery Challenge](https://github.com/sidharth0018) — one AI-assisted, interactive app built and shipped every day.

## What it is

A single-file, browser-based detective game that teaches marketing-campaign diagnosis through gameplay instead of a slide deck. The player is assigned a fictional company whose campaign underperformed, investigates an evidence board (metrics, budget, customer comments, social performance, and hidden clues), then has to name the one primary mistake that tanked the campaign — before reading a full data-backed explanation.

Live logic: 12 fully-written fictional marketing cases, each with reach/CTR/conversion data, channel budget splits, customer comments, social sentiment, a primary mistake, three supporting clues, a detailed explanation, and suggested fixes. A new case loads at random every replay.

## Why I built it this way

Most "learn marketing analytics" content is passive reading. Framing the same content as a case file you have to solve forces active pattern-recognition — you have to notice that CTR is healthy but conversion is not, and connect that gap to a specific clue, before the app tells you why. That's closer to how the diagnosis actually happens on the job.

## Tech stack

- React 18 (via CDN, `unpkg.com`) + Babel Standalone for in-browser JSX — no build step, no npm
- Vanilla CSS for the entire "premium dark detective" visual system: corkboard textures, sticky notes, push pins, paper stamps, animated bars
- Zero backend, zero API calls, zero external assets — fully offline-capable, single `.html` file
- Case data lives in a plain JS array (`CASES`), no database

## How to run

Download `marketing-detective.html` and open it directly in any modern browser. No install, no server.

## User flow

1. **Case Assignment** — dossier card reveals company, industry, objective, audience
2. **Investigation Board** — draggable evidence cards: metrics, budget, comments, social performance, 2 of 3 supporting clues
3. **Deep Investigation** — a sealed folder holds the third, hidden clue
4. **Accusation** — pick the primary mistake from 4 options (1 correct + 3 realistic distractors)
5. **Case Closed** — animated verdict stamp
6. **Learning Report** — full explanation, all clues, real customer quotes, suggested improvements, animated budget-allocation bars

## Screens

See `Day34.md` for annotated screenshots and a walkthrough of each stage.

## Files in this folder

| File | Purpose |
|---|---|
| `marketing-detective.html` | The full working app (open in browser) |
| `README.md` | This file |
| `LEARNINGS.md` | Technical + product decisions and what I'd change next |
| `Day34.md` | Day-by-day summary for the challenge log |
