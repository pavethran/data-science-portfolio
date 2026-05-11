# Week 1 — Indian Developers 2025: Salary and Work-Style

> What 1,846 Indian professional developers told Stack Overflow about their salaries and how they work in 2025.

**Author:** Pavethran Muthukumaran
**LinkedIn:** https://www.linkedin.com/in/pavethran-m/
**Live dashboard:** https://public.tableau.com/app/profile/pavethran.muthukumaran/viz/Week1IndianDeveloperCompensation2025/IndianDevelopers2025StackOverflowSurvey
**Date:** 2026-05-11

![Dashboard](Indian%20Developers%202025%20%E2%80%94%20Stack%20Overflow%20Survey.png)

---

## 1. The question

Two questions I wanted real numbers for, not vibes:

1. How does a professional Indian developer's salary scale with years of coding experience?
2. Is the "WFH war" narrative actually playing out in the data, or are Indian devs back in the office?

## 2. The data

| Item | Detail |
|---|---|
| Source | Stack Overflow Annual Developer Survey 2025 |
| Released by | Stack Exchange under Open Database License (ODbL) |
| Raw download | github.com/StackExchange/Survey/tree/main/packages/archive/2025 |
| Total responses | 49,000+ from 177 countries |
| Rows after my filters | 1,846 (India + professional developer only) |
| Currency filter | INR Indian rupee only |
| Salary range filter | ₹1 lakh to ₹5 crore (removes joke responses) |

## 3. How I cleaned it

1. Connected the 140 MB raw CSV directly to Tableau Public (skipped Excel — too slow at this size).
2. Filtered on the data source page: Country = India, MainBranch = "I am a developer by profession".
3. Changed `Comp Total` to numeric so I could aggregate it as a median.
4. Added a worksheet-level filter on `Currency` (INR only) and a range filter on `Comp Total` (₹1,00,000 to ₹5,00,00,000) to neutralise outliers.
5. Used MEDIAN, not SUM or AVG — medians ignore the small number of people who entered absurd salary numbers.

## 4. The 3 findings

1. **Salary compounds hard between years 8 and 19.** Median compensation roughly 8x in that span. Year 8 sits around ₹7 lakhs. Year 19 crosses ₹60 lakhs. The data does not show a flattening early career — it shows accelerating returns to staying technical.

2. **"Pure in-person" is the single biggest work-style at 29% (470 of 1,614 respondents).** More than pure remote (25%, 410 respondents). The popular "WFH won" narrative is not what the data actually says.

3. **But combined hybrid wins at 38% (615 respondents).** When you collapse "mostly remote" and "mostly in-person" into one bucket, hybrid is the largest work-arrangement overall. The future is not remote vs office — it is some-of-both.

## 5. The dashboard

**Open the interactive version:** https://public.tableau.com/app/profile/pavethran.muthukumaran/viz/Week1IndianDeveloperCompensation2025/IndianDevelopers2025StackOverflowSurvey

## 6. Tools used

- Stack Overflow 2025 Developer Survey (data)
- Tableau Public Desktop (visualisation)
- GitHub Desktop (version control and hosting)
- LinkedIn (publishing the writeup)

## 7. What I would do next

- Cross-reference `DevType` so the salary chart can split into Data Scientist, Web Developer, ML Engineer, etc. — currently it lumps all developer roles together.
- Add `EdLevel` as a colour dimension on the salary chart to see whether a Master's premium really exists.
- Compare 2025 vs 2024 vs 2023 surveys to see the actual hybrid trend over time, not a single snapshot.

## 8. Files in this folder

- `README.md` — this writeup
- `Indian Developers 2025 — Stack Overflow Survey.png` — dashboard screenshot
- `Week 1 – Indian Developer Compensation 2025.twb` — Tableau workbook (open in Tableau Public Desktop to inspect)

## 9. Credits and contact

If you have feedback, ideas, or a data role you think I would be good for, I respond fast:
- LinkedIn: https://www.linkedin.com/in/pavethran-m/
- Email: pavethranmuthukumaran@gmail.com

If this was useful, star the parent repo — it visibly helps me when I apply to roles.
