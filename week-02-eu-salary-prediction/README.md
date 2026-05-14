# Week 2 — Predicting EU Developer Salaries with ML

> Can a Random Forest beat a recruiter at guessing a Berlin developer's salary? I trained 3 models on 2,000+ DACH (Germany / Netherlands / Austria / Switzerland) professional developers and let SHAP tell me which features matter.

**Author:** Pavethran Muthukumaran
**LinkedIn:** https://www.linkedin.com/in/pavethran-m/
**Date:** Week 2 of 8 — May 2026

---

## 1. The question

1. How well can a model predict a DACH developer's annual salary from publicly available features (experience, education, company size, languages)?
2. Which features actually drive salary?
3. Does XGBoost beat a 30-line Random Forest, or is the difference noise?

## 2. The data

- Source: Stack Overflow Annual Developer Survey 2025 (same CSV as Week 1)
- Filter: Country in [Germany, Netherlands, Austria, Switzerland]
- Filter: MainBranch = "I am a developer by profession"
- Filter: ConvertedCompYearly between $20,000 and $300,000 (removes joke values)
- Expected rows: ~2,000
- Target: `ConvertedCompYearly`

## 3. Features

- Numeric: `YearsCodePro`, `YearsCode`, `Age` (midpoint of bucket)
- Ordinal: `EdLevel` (1=primary → 6=PhD), `OrgSize` (1=freelancer → 9=10k+)
- Multi-hot: top 12 programming languages
- One-hot: Country (4 countries)

## 4. Models compared

| Model | Why |
|---|---|
| Linear Regression | Baseline. If complex models can't beat this, complexity is not earning its keep. |
| Random Forest (300 trees) | Captures non-linearities + feature interactions without tuning hell. |
| XGBoost (500 rounds, depth 5) | Industry standard for tabular ML. |

Metrics on a held-out 20% test set: RMSE, MAE, R².

## 5. How to run

```bash
# 1. Place so_survey_2025.csv in this folder
# 2. Set up venv
python -m venv .venv && .venv\Scripts\activate   # Windows
# 3. Install
pip install -r requirements.txt
# 4. Run
jupyter notebook eu_salary_prediction.ipynb
```

## 6. Tools

Python 3.10+ · pandas · numpy · scikit-learn · xgboost · shap · matplotlib · seaborn · jupyter

## 7. Files

- `README.md` — this writeup
- `requirements.txt` — Python deps
- `eu_salary_prediction.ipynb` — full ML notebook
- `so_survey_2025.csv` — raw data (gitignored)
- `eu_salary_xgb_model.joblib` — saved model (generated)
- `shap_summary.png`, `predicted_vs_actual.png` — plots (generated)

## 8. Status

🛠 Building — notebook scaffolded, results coming Saturday.

## 9. Contact

- LinkedIn: https://www.linkedin.com/in/pavethran-m/
- Email: pavethranmuthukumaran@gmail.com

Berlin / EU data-science recruiters: if this kind of work matches what your team needs, I am open to chat.
