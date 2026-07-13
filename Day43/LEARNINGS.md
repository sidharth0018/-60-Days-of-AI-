## Day 43 — AI Workflow Architect

**What I learned:**
- Structuring an AI generation flow around explicit MCQ-based elicitation (one question at a time) produces far more scoped, useful output than a single freeform prompt — the narrowing itself is part of the product.
- A single-page app can act as a genuine *deliverable*, not just a demo — treating a career pipeline as an interactive artifact (checklists, notes, persistence) makes it something I'll actually reuse, not just look at once.
- Design restraint matters: resisting the "cream background + terracotta accent" AI-default look forced more intentional palette/type choices tied to the actual subject (a pipeline/rail metaphor).

**Technical takeaway:**
- `localStorage` is enough to make a static HTML tool feel like a real stateful app (progress %, per-stage checklists, saved notes, theme) with zero backend.

**Challenge:**
- Balancing depth (6 stages × 10 content types) against file size and readability — solved by rendering all stage content from a single JS data array instead of hardcoding repetitive HTML blocks.
