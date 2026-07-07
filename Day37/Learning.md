# Day 37 Learnings — Task Compass (Café Edition)

## What I Built
A single-file HTML/CSS/JS simulation teaching organizational workflow concepts (ownership, delegation, routing, collaboration) using a café/restaurant scenario set, built from a detailed structured prompt spec.

## Key Technical Learnings

### 1. Designing state machines for multi-stage apps without a framework
With no React, the whole app runs on one `state` object and a `render<Screen>()` function per screen that fully re-renders `innerHTML`. This is a simpler mental model than component state, but requires being disciplined about re-attaching event listeners after every re-render — DOM nodes created via `innerHTML` don't retain JS listeners from the previous render.

### 2. Drag-and-drop + click fallback in the same interaction
Built native HTML5 Drag-and-Drop (`dragstart`/`dragover`/`drop`) for desktop, but added a parallel `click` handler on the same role cards so the app doesn't break on touch devices (mobile Safari/Chrome have inconsistent native DnD support). Same underlying `placeRole()` function services both input paths — avoided duplicating logic.

### 3. Scoring qualitative behavior, not just correctness
Stage 1 rewards the *correct* owner but still gives partial delegation credit if the picked role appears in the task's "assist" list — because in real workflows, a "wrong but plausible" answer isn't the same failure as a random guess. This required tracking `scores` and `scoreMax` separately per category so percentages stay meaningful even when categories accumulate points differently across stages.

### 4. Sequence-scoring for the workflow stage (Stage 2)
Rather than requiring an exact array match, I scored the player's sequence against a canonical "correct" order using a relative-order heuristic: count how many picked roles appear in the *correct relative order* they'd occur in the canonical path. This is more forgiving and realistic than exact-match — multiple valid routings can exist in real organizations.

### 5. Reused CSS variables for a distinct café identity
Avoided the generic dark-mode-with-terracotta-accent AI-default look by intentionally choosing an espresso/gold/steam-green palette and a dashed "order ticket" motif for task cards — small thematic choices (ticket stub styling, "☕ ORDER TICKET" label) that make it feel like a café-specific tool rather than a reskinned generic template.

## Challenges Faced
- Balancing partial-credit scoring logic so it felt fair without becoming overly generous (a single-role answer to a 4-role collaboration scenario needed to visibly under-score).
- Keeping the single HTML file readable — organized as DATA → STATE → RENDER HELPERS → per-stage render/logic → RESULTS, to keep the 900+ lines navigable without modules.

## Skills Reinforced
- Vanilla JS state management patterns (render-on-state-change)
- Native browser APIs (Drag-and-Drop) instead of reaching for a library
- Designing scoring systems that reflect *reasoning quality*, not just right/wrong
- Applying frontend design principles (distinct palette, thematic copy) instead of defaulting to templated dark-mode UI

## Relevance to Data Analyst / Data Science Path
This exercise is fundamentally about **modeling a decision process as structured data** (role ownership rules, workflow sequences, weighted category scoring) — the same underlying skill as building a scoring rubric, a RACI matrix, or a rules-based classification system in an analytics context. It's a good talking point for interviews about structured problem decomposition.
