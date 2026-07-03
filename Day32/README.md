# Day 32 — Think Like a Marketing Strategist: Grow This Brand

**#ABTalks60DayClaudeAIChallenge — Day 32/60**

An interactive, single-file React app that teaches marketing *strategy* — not content generation. Instead of asking Claude to "write me some posts," this app forces the user to make the same sequence of decisions a real marketing strategist makes: define the audience, choose platforms with tradeoffs, commit to only 3 content pillars, plan a month by weekly goals, and react to an unexpected event.

🔗 **Live demo:** open `index.html` directly in any browser — no server, no build step, fully offline after first load.

---

## Why I built this

Most "AI marketing tools" generate captions. They skip the actual thinking a strategist does *before* any content gets written. I wanted to build something that teaches the thinking process itself — including for people like me who don't have a business yet, but do have a skillset and a story to build a personal brand around.

This is also literally the app I used to build my own personal brand strategy (see the Growth Report screenshot below) — so Day 32 doubles as a real planning session for my own Data Analyst / Data Science job search brand.

---

## What it does

### 1. Three entry modes
- 🏢 **Use My Own Business** — bring a real business/product
- 🙋 **Build My Personal Brand** — use your own name, niche, and story as the "product" (this is the mode I used for myself)
- 🎲 **A New Client Has Arrived** — randomly generates a full business brief (industry, audience, budget, competitors, challenge) so you can practice on a cold scenario

### 2. A 7-step strategist flow
1. **Understand the audience** — forces specificity, not "everyone"
2. **Choose platforms** — each platform is labeled Strong Fit / Situational / Weak Fit with a plain-language reason (personal brand mode weights LinkedIn, X/Twitter, YouTube, and newsletters higher)
3. **Pick exactly 3 content pillars** out of 6 — each pillar states which business/brand goal it serves (awareness, trust, or conversion)
4. **30-day roadmap** — 4 *weekly strategic goals*, not a list of individual posts. Personal brand Week 1 is always "define your POV + optimize your bio"
5. **Unexpected event** — a randomly generated curveball (viral post, podcast invite, competitor copying your content, public disagreement, PR issue, budget cut). The user picks a response and sees a real consequence, not just a pat on the back
6. **Growth Report** — Audience Understanding, Platform Strategy, Content Strategy, Growth Potential, Best Decision, Biggest Risk/Mistake, and 3 personalized marketing lessons

### 3. "How to ask Claude" prompt cards
After every major step, the app shows a **reusable, copy-pasteable prompt** for that exact decision — so the person isn't just learning marketing, they're learning how to *prompt an AI* to think through marketing decisions with them, instead of just asking it to output content.

---

## Tech stack

- Single `.html` file — **React 18 + Babel Standalone**, both via CDN
- No Tailwind, no npm, no backend, no external APIs
- Pure CSS custom properties for a dark, modern theme (deep navy background, growth-green accent for "good" signals, amber for risk/mistake signals)
- Fully responsive, replayable (every session can pick a new random business or re-run a personal brand)
- State handled entirely with `useState` / `useMemo` — one root `<App />` component composed of small reusable pieces (`WhyBox`, `PromptCard`, `ProgressBar`, `GrowthChart`, choice grids, etc.)

## Design decisions worth calling out

- **"Why does this matter?"** callouts after every step — the app never lets a decision pass without explaining the underlying strategist logic, since the goal is teaching thinking, not just producing an output
- **Hard constraint of exactly 3 pillars** — deliberately forces prioritization instead of letting the user hoard every idea
- **Consequences, not just praise** — every response to the random event has a real tradeoff described, because real strategy involves cost, not just "good job"
- **Mode-aware content everywhere** — literally every stage (audience copy, platform weighting, pillar set, Week 1 roadmap goal, event pool, report lessons) branches based on Business vs. Personal Brand vs. Random Client, so the personal branding path never feels like a business template with names swapped in

---

## What I personally got out of running it on myself

I ran the **Build My Personal Brand** mode as *Sidharth* — Data Analyst / Data Science job seeker. My own Growth Report flagged:
- **Best decision:** leading with a **Thought Leadership** pillar to build credibility with recruiters/peers directly, instead of chasing reach first
- **Biggest risk to watch:** my simulated response to a "someone is copying your content style" event ("go deeper and more personal") is high-reward but needs consistency to actually outpace a copycat
- **Platform strategy:** LinkedIn, X/Twitter, and Instagram — validating what I already suspected, that LinkedIn should be my primary channel for a Data Analyst job search brand, not a secondary one

See `LEARNINGS.md` for the full breakdown of what building (and using) this app taught me.

---

## Files in this folder

| File | Purpose |
|---|---|
| `index.html` | The full app — single file, open directly in a browser |
| `README.md` | This file |
| `LEARNINGS.md` | What I learned building + using this on Day 32 |
| `growth-report-screenshot.png` | My own personal brand Growth Report output |

---

## Part of

**ABTalks 60-Day Claude AI Mastery Challenge** — daily AI-assisted builds, documented on [GitHub](https://github.com/sidharth0018) and LinkedIn.

Previous days in this repo cover healthcare workflow simulators (Prior Authorization, Hospital Admission Readiness) and supply chain simulation apps (Crisis Lab, Supply Chain Builder). Day 32 shifts into marketing strategy education — same build pattern, new domain.
