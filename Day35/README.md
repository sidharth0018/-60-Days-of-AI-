# 🧩 Prompt Puzzle — Master AI Prompting Through Play
### Day 35 of #ABTalks60DayClaudeAIChallenge

An interactive, single-file HTML game that teaches AI prompt engineering through drag-and-drop puzzles, prompt-cleaning challenges, and "choose the best prompt" quizzes — built entirely offline with vanilla JS.

## 🎯 What It Does
Prompt Puzzle turns prompt engineering theory into a playable game. Users pick a domain (Data Analysis / Data Science, Marketing, Software Dev, Creative Writing) and a difficulty level, then work through 6 scenarios across 3 challenge types:

1. **Build the Prompt** — drag correct prompt blocks into place while avoiding distractor blocks that sound helpful but weaken output quality.
2. **Clean the Prompt** — take a bloated, over-engineered prompt and strip it down to its essential, high-signal components.
3. **Choose the Best Prompt** — pick the optimized version from a set of weak / optimized / over-engineered options.

At the end, users get a full **Prompt Performance Report**: score, rating, rank, a "Prompt DNA" visualization (Specificity, Structure, Efficiency, Speed), personalized feedback, and a final optimized prompt example.

## 🖥️ Tech Stack
- Pure HTML, CSS, vanilla JavaScript (no frameworks, no CDN dependencies)
- Single-file architecture — works fully offline, just open the `.html` file
- Native drag-and-drop API + click-to-add fallback for mobile
- Object-based scenario data structure for easy content scaling

## 🎮 How to Use
1. Download `prompt-puzzle.html`
2. Open it in any browser — no server, no internet required
3. Answer the two setup questions (domain + difficulty)
4. Play through all scenarios and review your Performance Report
5. Hit Replay for a freshly randomized run

## 📊 Scoring System
- **Accuracy** — correctness of block placement / prompt choice
- **Time** — small penalty for slow decisions
- **Moves** — total interactions tracked
- **Wrong Placements** — distractor blocks dragged in (penalty)
- **Hints Used** — optional help at a point cost
- **Optimization Bonus** — extra points for clean, hint-free, mistake-free runs

## 🧠 Why I Built This
As someone actively prepping for Data Analyst / Data Science roles, I wanted a tool that makes the *difference between a weak prompt and an optimized one* concrete and visceral — not just theoretical. Building it also forced me to articulate prompt engineering principles (specificity, role framing, output formatting, audience framing) clearly enough to teach them.

## 🔗 Part of the Challenge
Day 35 of my 60-Day Claude AI Mastery Challenge — one AI-assisted, fully documented app every day.
