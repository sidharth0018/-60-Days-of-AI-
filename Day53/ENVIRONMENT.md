# FraudLens — Environment Configuration

## Runtime
- **Python:** 3.9+ (no framework CLI needed — Streamlit runs via its own command, not a project generator)

## requirements.txt (pinned)
```
pandas
numpy
scikit-learn
imbalanced-learn
matplotlib
seaborn
jupyter
ipykernel
streamlit
joblib
```
> No exact versions pinned yet at Day 3 — will be frozen with `pip freeze > requirements.txt` on Day 9 right before deployment, once the final working combination is confirmed. This avoids chasing version conflicts mid-build.

## Environment Variables
**None required for v1.0.** No API keys, no database connection strings, no secrets.

This is a deliberate consequence of the architecture (Day 2): the model runs locally as a saved artifact, there's no external AI API call, no database, and no authentication — so there's nothing that needs a `.env` file or Streamlit secrets in v1.0.

If this changes later (e.g., Future Scope adds a live API), secrets would go in `.streamlit/secrets.toml` (gitignored) — noting this now so the pattern is documented even though it's unused today.

## VS Code Extensions
| Extension | Purpose |
|---|---|
| Python (Microsoft) | Syntax highlighting, linting, IntelliSense |
| Jupyter (Microsoft) | Run `.ipynb` notebooks directly inside VS Code |

## Configuration Files
| File | Purpose |
|---|---|
| `.gitignore` | Excludes `data/raw/`, `venv/`, `__pycache__/`, `.ipynb_checkpoints/` |
| `.streamlit/config.toml` | App theming — created Day 8, not needed yet |
| `requirements.txt` | Dependency list — created today, frozen Day 9 |

## External Accounts Needed
| Service | Why | Cost |
|---|---|---|
| Kaggle | Manual dataset download | Free |
| GitHub | Source control + deployment trigger | Free |
| Streamlit Community Cloud | Hosting (Day 9) | Free |
