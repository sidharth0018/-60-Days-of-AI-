# FraudLens — Setup Guide

## Prerequisites
- Python 3.9+
- Git
- A free Kaggle account (for dataset download)
- VS Code (recommended) with Python + Jupyter extensions, or any IDE with Jupyter support

## 1. Clone the repository
```bash
git clone https://github.com/sidharth0018/FraudLens.git
cd FraudLens
```

## 2. Create and activate a virtual environment
```bash
python -m venv venv
```
Windows: `venv\Scripts\activate`
Mac/Linux: `source venv/bin/activate`

## 3. Install dependencies
```bash
pip install -r requirements.txt
```

## 4. Download the dataset
1. Go to https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud (Kaggle account required, free).
2. Click **Download**.
3. Extract `creditcard.csv` into `data/raw/` in this repo.
   > This file is intentionally excluded from git via `.gitignore` — it's ~150MB and not something we want in version control.

## 5. Launch Jupyter and verify
```bash
jupyter notebook
```
Open `notebooks/01_eda.ipynb` and run the first cell (load + shape check). If it prints the dataset shape with no errors, setup is complete.

## 6. Run the Streamlit app (once it exists, Day 7+)
```bash
streamlit run app.py
```

## Troubleshooting
| Issue | Fix |
|---|---|
| `python` not recognized | Reinstall Python, check "Add to PATH" during install |
| `pip install` fails on a package | Upgrade pip first: `python -m pip install --upgrade pip` |
| Jupyter can't find the venv kernel | Run `python -m ipykernel install --user --name=fraudlens-venv` after activating venv |
| `FileNotFoundError` on dataset load | Confirm `creditcard.csv` is in `data/raw/`, not `data/` |
