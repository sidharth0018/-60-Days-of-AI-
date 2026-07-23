# Day 51 — Learnings

## 1. Constraints-first beats idea-first
Asking about time budget, skill level, and deployment experience *before* proposing a project prevented picking something exciting but unrealistic. The project was fitted to the builder, not the other way around.

## 2. "Prove what's missing," not "prove what's already proven"
Existing portfolio projects already demonstrate data-analysis framing (hardware projects reframed for DA roles). This capstone was deliberately scoped to prove a *different* skill — applied ML/classification — so the portfolio has range instead of repetition.

## 3. Hard non-goals prevent scope creep before it starts
Writing down explicit "out of scope for v1.0" items (deep learning, real-time streaming, full SHAP, auth) up front — before excitement about the project could cause feature creep — makes it much easier to say no on Day 6 when time is tight.

## 4. Imbalanced classification is a better beginner project than it sounds
Picking credit card fraud detection seemed like the "harder" option, but the standard dataset is already numerically pre-processed (PCA features), which removes messy feature engineering and lets the learning focus stay on the actually-important skill: correctly evaluating and handling class imbalance.

## 5. A one-paragraph confirmation checkpoint saves rework
Summarizing the finalized project in a single paragraph and getting explicit approval before generating any deliverable avoided the risk of building a full PRD around a misunderstood direction.

## 6. Deployment platform choice is a scoping decision, not just a technical one
Choosing Streamlit Community Cloud wasn't about which tool is "best" — it was about matching the deployment method to zero prior deployment experience, so Day 8–9 doesn't become a DevOps detour.
