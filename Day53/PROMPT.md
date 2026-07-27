# Day 53 — Reusable Prompt: Project Setup & Foundation

Use this prompt on Day 3 of any capstone to build a working development foundation before feature implementation begins.

---

## The Prompt

Today is Day 3, continuing the same capstone. Before doing anything, read the following documents from the previous days: PRD, 10-Day Blueprint, System Design Documents, Architecture, Database Design, API Design, Project Structure. These documents are now the source of truth. Do not redesign the project unless a critical issue is discovered. If any document is unavailable, ask me to upload it.

### Standing Rules
- Assume I need guidance for every manual step unless I tell you otherwise.
- Whenever I need to perform a task outside this chat, explain it using the exact buttons, menus, commands, and terminal instructions.
- Wait for my confirmation and a screenshot before continuing.
- Never assume I've completed a manual step.
- Explain every technical concept in beginner-friendly language before using it.

### Today's Goal
Build the project's foundation. By the end of today: development environment fully configured, project running locally, complete folder structure, Git repository initialized and connected, dependencies installed, configuration files completed, database connected (if required), authentication scaffolded (if required), basic navigation/routing working, and a working "Hello World" version running successfully. Do not begin implementing core features yet unless the Blueprint specifically schedules a small foundation feature. Follow the Day 3 section of the 10-Day Blueprint while adapting to any issues that arise.

### Complete the Following
1. **Environment Setup** — runtime, IDE extensions, package managers, framework CLI, SDKs, environment variables. Explain why each tool is needed.
2. **Project Initialization** — create the project, install dependencies, initialize configuration, run the project, verify everything works.
3. **Repository Setup** (if not already done) — connect to GitHub, create branches, explain the branching strategy, make the initial commit.
4. **Build the Foundation** — only foundational pieces (routing, layout, navigation, auth scaffold, database connection, API client, shared components, state management, configuration) — and only the ones the actual architecture requires. Explain every major file created.
5. **Verify the Project** — confirm it builds, runs with no errors, matches the System Design, and is ready for feature development tomorrow. Debug any problems before moving on.

### Deliverables
Generate downloadable versions of: `SETUP.md`, `PROJECT-STRUCTURE.md` (if changed), `ENVIRONMENT.md`, `DAY3-SUMMARY.md`. Update the 10-Day Blueprint if today's implementation required changes.

### End of Day
Commit today's work with a meaningful message, push to GitHub, update the project log, and write a LinkedIn post. Summarize: ✅ what was completed, 🚧 what's ready to build tomorrow, 🎯 tomorrow's objective.

---

## Why This Prompt Works
- Reading prior-day docs as source of truth prevents Day 3 from silently drifting from the approved design
- "Only the pieces the architecture requires" stops generic checklists from adding unnecessary scaffolding
- The explicit verification gate before closing the day prevents false progress in the log
