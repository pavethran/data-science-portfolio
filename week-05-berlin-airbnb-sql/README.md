# Week 5 — Berlin's Airbnb Market: A SQL Deep-Dive

A **SQL-driven analysis of 12,855 Berlin Airbnb listings** across 12 Bezirke and 138 neighbourhoods. Ten progressive queries — from simple aggregates to CTEs and window functions — answer real business questions and surface three findings most people miss.

> **The question:** What does the Berlin Airbnb market actually look like, once you stop reading tourist blogs and start reading the data?

## Three findings that surprise most people

1. **The market is nearly half commercial.** Only **53.6%** of listings come from single-property "genuine" hosts. The rest are multi-property operators, including **11%** from operators running 20+ listings (Blueground alone has 261).
2. **The pricing paradox.** Listings that are booked out (0 days available) average **€103/night**. Listings available all year average **€169** — 64% more. The premium listings are the ones sitting empty.
3. **Two Bezirke rule.** Mitte + Friedrichshain-Kreuzberg = **43%** of the whole market. Add Pankow and you cover **58%** of all Berlin Airbnbs in 3 of 12 Bezirke.

## What the notebook demonstrates (SQL-wise)

| # | Query | SQL technique |
|---|---|---|
| Q1 | Market size (listings, hosts, avg + median price) | Aggregate + subquery for median |
| Q2 | Bezirke share | `GROUP BY` + calculated percentages |
| Q3 | Price by room type | `WHERE` + `GROUP BY` + multiple aggregates |
| Q4 | Median price per Bezirk | **CTE + `ROW_NUMBER()` window function** |
| Q5 | Power hosts (10+ listings) | `GROUP BY` multiple + `HAVING` + `LIMIT` |
| Q6 | Most-reviewed neighbourhoods | `GROUP BY` + `HAVING` + calculated ratios |
| Q7 | Commercial vs genuine split | `CASE WHEN` bucketing + percentages |
| Q8 | Entire-home vs private-room premium by Bezirk | **CTE + self-JOIN** |
| Q9 | Top 3 neighbourhoods within each Bezirk | **CTE + `RANK() OVER (PARTITION BY ...)`** |
| Q10 | Availability paradox | `CASE WHEN` bucketing + cross-tab |

## The data

- **Source:** [Inside Airbnb — Berlin](http://insideairbnb.com/berlin)
- **Snapshot:** August 2025 (`listings.csv` summary, ~5 MB)
- **Grain:** one row per listing (12,855 rows, 19 columns)
- **Companion table:** `neighbourhoods.csv` (139 neighbourhoods across 12 Bezirke, for joins)

## What's in this repo

| File | Purpose |
|---|---|
| `berlin_airbnb_sql.ipynb` | The full executed notebook — 10 SQL queries + charts + findings |
| `berlin_listings.csv` | The listings data |
| `berlin_neighbourhoods.csv` | Neighbourhood → Bezirk lookup |
| `chart_*.png` | Exported charts |
| `requirements.txt` | Python dependencies |
| `README.md` | This file |

## Run it yourself

```bash
pip install -r requirements.txt
jupyter notebook berlin_airbnb_sql.ipynb
```

Notebook builds an **in-memory SQLite database** from the CSVs on load — no external DB or setup required. Just keep the CSVs next to the notebook and Run All.

## Tools

**SQL** (SQLite) · **Python** · pandas · matplotlib · seaborn · Jupyter

---

**Author:** Pavethran Muthukumaran · [LinkedIn](https://www.linkedin.com/in/pavethran-m/)
*Week 5 of my weekly data-science portfolio — SQL deep-dive edition.*
