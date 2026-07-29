# Day 58 — Learnings

## 1. A blocked project needs a different move than "try the next day's prompt"
Advancing to Day 7 and Day 8 didn't move the project forward — it just produced two more logs describing the same stuck point. The right response to being blocked is to stop and resolve the blocker, not to keep issuing new day-prompts hoping momentum resumes on its own.

## 2. Public build logs should reflect reality, even when it's not flattering
It would be easy to quietly stop logging blocked days and only publish the ones with real progress. But an honest, continuous log — including the stuck points — is actually a more credible signal to a recruiter than a suspiciously smooth, gap-free history.

## 3. One unresolved checkpoint can stall an entire pipeline
Every subsequent day depended on the same single artifact (`finalize_model.py`'s output). This is a good real-world lesson in dependency chains: identifying the true root blocker early saves repeatedly re-discovering the same symptom downstream.
