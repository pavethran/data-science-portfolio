# Week 2 — Predicting EU Developer Salaries with ML

> Can a Random Forest beat a recruiter at guessing a Berlin developer's salary? I trained 3 models on 2,696 DACH (Germany / Netherlands / Austria / Switzerland) professional developers and let SHAP tell me which features matter.

**Author:** Pavethran Muthukumaran
**LinkedIn:** https://www.linkedin.com/in/pavethran-m/
**Date:** Week 2 of 8 — May 2026

---

## 1. The question

1. How well can a model predict a DACH developer's annual salary from publicly available features?
2. Which features actually drive salary?
3. Does XGBoost beat a plain Random Forest, or is the difference noise?

## 2. The data

- Source: Stack Overflow Annual Developer Survey 2025 (same CSV as Week 1)
- Filter: Country in [Germany, Netherlands, Austria, Switzerland], professional developers only
- Filter: ConvertedCompYearly between $20,000 and $300,000 (removes joke values)
- Final sample: **2,696 developers** (Germany 1,658 / Netherlands 503 / Switzerland 314 / Austria 221)
- Target: annual compensation in USD
- Note: the 2025 survey renamed `YearsCodePro` to `WorkExp` — the notebook patches for this.

## 3. Models & results

| Model | RMSE | MAE | R² |
|---|---|---|---|
| Linear Regression | $37,204 | $25,161 | 0.287 |
| **Random Forest** (winner) | **$36,354** | **$24,152** | **0.319** |
| XGBoost | $37,119 | $25,236 | 0.290 |

All three models landed within ~$850 RMSE of each other. XGBoost did not meaningfully beat the simpler models.

## 4. The 3 findings

1. **The simple model won.** Random Forest edged out XGBoost, and all three models were within $850 RMSE. The gradient-boosted model did not earn its extra complexity here — reach for the simple model first.

2. **The best model only explains 32% of salary variance.** The other 68% is driven by things no survey captures — negotiation, the specific employer, individual performance. Honest modelling means stating what you cannot predict.

3. **Location and experience beat your tech stack 3–4x.** SHAP mean impact: being in Switzerland +$10,229, years of work experience +$9,152, company size +$5,835. The highest-impact programming language (JavaScript) was only +$2,933.

## 5. SHAP feature importance (mean |SHAP|, USD)

| Rank | Feature | Impact |
|---|---|---|
| 1 | Country = Switzerland | $10,229 |
| 2 | Years of work experience | $9,152 |
| 3 | Company size | $5,835 |
| 4 | Years coding | $5,032 |
| 5 | Language: JavaScript | $2,933 |
| 6 | Language: Go | $2,181 |
| 7 | Country = Germany | $2,028 |
| 8 | Language: C# | $2,016 |

## 6. How to run

```bash
# Easiest: open the notebook in Google Colab (one click from GitHub)
# It auto-downloads the dataset and installs dependencies.

# Or locally:
python -m venv .venv && .venv\Scripts\activate   # Windows
pip install -r requirements.txt
jupyter notebook eu_salary_prediction.ipynb
```

## 7. Tools

Python 3 · pandas · numpy · scikit-learn · xgboost · shap · matplotlib · seaborn

## 8. Files

- `README.md` — this writeup
- `eu_salary_prediction.ipynb` — full executed notebook (load → clean → model → SHAP)
- `requirements.txt` — Python dependencies

## 9. What I would do next

- Add `RemoteWork`, `Industry`, `DevType` as features — likely lifts R² above 0.35.
- Widen the salary filter and check whether XGBoost handles the tails better.
- Wrap the model in a Streamlit app for a "predict my salary" demo.

## 10. Status

✅ **Complete** — notebook executed, 3 models trained, results above.

## 11. Contact

- LinkedIn: https://www.linkedin.com/in/pavethran-m/
- Email: pavethranmuthukumaran@gmail.com

Berlin / EU data-science recruiters: if this kind of work matches your team, I am open to chat.
