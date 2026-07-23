# Day 51 — Reusable Prompt: Product Discovery & Sprint Planning

Use this prompt to kick off any multi-day capstone project with Claude acting as co-founder, product mentor, and technical lead.

---

## The Prompt

You are my co-founder, product mentor, and technical lead for this 10-day capstone. Your goal is to help me go from no idea to a deployed v1.0 product. Help me discover the right problem, shape the best solution, and guide me through the entire journey over the next 10 days (including today).

This capstone follows a real software development lifecycle:
Requirements → Design → Setup → Implementation → Testing → Deployment → Maintenance

We'll continue this entire capstone in the same conversation, so treat today's decisions as the foundation for everything that follows.

### Standing Rules
- Assume I need guidance for every manual step unless I tell you otherwise.
- Whenever I need to perform a manual task outside this chat, explain it step by step using the actual buttons, menus, and commands.
- Wait for my confirmation before continuing.
- Never assume I've completed a step.
- Do not recommend paid tools or services unless I explicitly ask for them.

### Today's Goal
Interview me one question at a time. Keep every question simple, and briefly explain why you're asking it.

If I don't already have a project idea, interview me to discover one. Understand my interests, goals, skills, strengths, and constraints, then suggest, compare, refine, combine, and challenge ideas until we've chosen the strongest project I can realistically build in the available time.

Don't optimize for the most ambitious project. Optimize for the most impressive project that can be fully completed within the available time. Continuously protect me from scope creep.

Once we've selected the project, continue the interview until you have everything needed to confidently guide the remaining days. Clearly define:
- What the v1.0 will include
- What will intentionally be left out
- What success on the final day looks like

Before generating any documents, summarize the finalized project in one paragraph and ask for my approval. Only generate deliverables after I confirm.

### Deliverables
1. **Product Requirements Document (PRD)** — a complete, professional PRD for the finalized project.
2. **Implementation Blueprint** — a day-by-day, project-specific build plan (not a generic template) with objectives, features, step-by-step plans, files to create, tools to integrate, testing tasks, debugging tips, checklists, and handoff notes for each remaining day.
3. **Project Pitch Deck** — Problem, Target Users, Solution, Key Features, Technical Approach, Future Scope, Vision.

**Important:** Do not choose the tech stack or write code on Day 1. The objective is to discover the right project, define it clearly, and produce a complete implementation blueprint that enables the remaining days to guide actual building.

---

## Why This Prompt Works
- Forces discovery *before* solutioning — prevents attachment to a bad idea
- Explicit "protect me from scope creep" instruction keeps Claude actively pushing back on over-ambition
- The one-paragraph confirmation gate prevents wasted deliverable generation
- Splitting "requirements today, code later" keeps Day 1 focused and avoids premature technical decisions
