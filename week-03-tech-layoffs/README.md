# Week 3 — Are Tech Layoffs a Sign of Failure?

An exploratory data analysis (EDA) of **4,418 tech layoff events** from **March 2020 to May 2026**.

> **The question:** When a company announces layoffs, everyone assumes it's in trouble.
> Is that what the data actually shows? It turns out the answer depends almost entirely on
> one variable — and it isn't the economy.

## Headline findings

1. **Layoffs aren't a recession story — they're a post-pandemic wave that never broke.**
   2020 (COVID) cut ~81k jobs; 2021 went quiet at 16k; then it exploded — 165k (2022),
   a record **264k (2023)**, and it hasn't stopped. 2026 is on pace for ~296k.

2. **The biggest layoffs come from the healthiest companies.** Mature, public "Post-IPO"
   companies are just **24% of layoff events but 63% of all jobs cut**. The 12 companies
   behind the largest cuts are Amazon, Intel, Meta, Oracle, Microsoft, Dell, Cisco,
   Salesforce, Tesla, Google — all profitable giants.

3. **"Layoff" hides two opposite events.** A mature company cuts a median **10%** of staff
   (a trim). A seed-stage startup cuts a median **100%** (it shuts down). 348 companies in
   the data laid off everyone.

**The answer:** for the big public companies that generate most of the headlines, a layoff
is increasingly an efficiency / margin decision — and now an AI-restructuring one — not a
distress signal. The companies genuinely failing are the small startups.

## The data

| | |
|---|---|
| **Source** | Layoffs Dataset (Kaggle), built from [layoffs.fyi](https://layoffs.fyi) public reporting |
| **Grain** | One row per layoff event |
| **Rows** | 4,418 events · 2,913 companies · 66 countries |
| **Window** | 11 Mar 2020 – 21 May 2026 |
| **Key fields** | `company`, `total_laid_off`, `percentage_laid_off`, `date`, `industry`, `stage`, `funds_raised`, `country` |

## What's in the notebook

`layoffs_eda.ipynb` walks through the analysis end to end:

- **Load & clean** — parse dates, derive year/month, flag missing headcounts
- **When** — layoffs by year and month, with a 2026 full-year projection
- **Who** — layoffs by funding stage, the Post-IPO concentration, funding vs. layoff size, top companies
- **How deep** — median % of staff cut by stage, shutdown count
- **Context** — industries, and the emergence of "AI" as a layoff category
- **The answer** — what it all means, plus honest limitations

## Charts

| File | Shows |
|---|---|
| `chart_by_year.png` | Jobs cut per year, 2020–2026 (+ projection) |
| `chart_monthly.png` | Monthly layoff trend |
| `chart_postipo.png` | Post-IPO: 24% of events, 63% of jobs cut |
| `chart_funds.png` | Funding raised vs. median layoff size |
| `chart_companies.png` | Top 12 companies by jobs cut |
| `chart_stage_pct.png` | Median % of workforce cut, by stage |
| `chart_industry.png` | Jobs cut by industry |

## How to run

```bash
pip install -r requirements.txt
jupyter notebook layoffs_eda.ipynb
```

Keep `layoffs.csv` in the same folder as the notebook, then **Run All**.

## Tools

Python · pandas · numpy · matplotlib · seaborn · Jupyter

## Files

| File | Description |
|---|---|
| `layoffs_eda.ipynb` | The full EDA storytelling notebook (executed, with charts) |
| `layoffs.csv` | The dataset |
| `requirements.txt` | Python dependencies |
| `chart_*.png` | Exported charts |

## Notes & limitations

- `total_laid_off` is missing for ~34% of events — all totals are a **disclosed floor**.
- The data skews toward US tech (~71% of disclosed cuts are US-based).
- `stage` is a company's *last known* funding stage, not its state on the layoff date.
- This is **descriptive** analysis: it surfaces patterns, not causes.

---

**Author:** Pavethran Muthukumaran · [LinkedIn](https://www.linkedin.com/in/pavethran-m/)
*Week 3 of my weekly data-science portfolio.*
