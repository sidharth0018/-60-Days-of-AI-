# Day 53 — Learnings

## 1. "Foundation" means different things for different architectures
A generic Day 3 checklist (routing, auth, DB) is written for a typical CRUD web app. Applying it blindly to an ML/Streamlit project would have meant building infrastructure the project will never use. Reading the actual architecture doc first — and adapting the checklist to it — produced a foundation that's genuinely useful instead of generic busywork.

## 2. `.gitignore` set up early pays off immediately
Because `.gitignore` was configured on Day 2, downloading the ~150MB dataset today was a non-event — no risk of accidentally committing it, no cleanup needed. Order of operations matters more than most people expect in project setup.

## 3. Verification checkpoints prevent false progress
Waiting for an explicit "yes, it all works" confirmation before writing the Day 3 summary — instead of assuming setup succeeded — meant the summary document is actually trustworthy, not just optimistic.

## 4. Deferring version pinning is a legitimate choice, not laziness
Not pinning exact package versions on Day 3 was a deliberate decision to avoid chasing dependency conflicts mid-build. Freezing `requirements.txt` is scheduled for Day 9, right before deployment, when the final working combination is actually known.

## 5. A "Hello World" doesn't have to be a running server
For a data science project, the equivalent of a "Hello World" app is a notebook that loads real data and confirms the pipeline entry point works — reframing this instead of forcing a literal running web app kept today's goal honest and achievable.
