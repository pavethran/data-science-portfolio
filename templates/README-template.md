# Week XX — <Project Title>

> One-line hook: e.g. *"I analysed 500 Indian Data Scientist job postings to find out which skills actually matter in 2026."*

**Author:** Pavethran Muthukumaran
**LinkedIn:** https://www.linkedin.com/in/pavethran-m/
**Live dashboard:** <paste Tableau Public link here>
**Date:** YYYY-MM-DD

---

## 1. The question

What specific, narrow question did this week's project answer?

Example: *"Out of 500 Data Scientist jobs posted in India in the last 30 days, which technical skills are required most often, and how does that differ between Bangalore and the rest of India?"*

## 2. The data

| Item | Detail |
|---|---|
| Source | LinkedIn job postings (public) |
| Tool used to collect | Apify — `bebity/linkedin-jobs-scraper` actor |
| Date collected | YYYY-MM-DD |
| Number of rows | 500 |
| Columns kept | title, company, location, postedAt, description, jobUrl |

Raw file: `week-XX-name/weekXX_raw_jobs.csv`
Cleaned file: `week-XX-name/weekXX_clean.xlsx`

## 3. How I cleaned it

In 3–5 short bullets, explain the cleaning steps. Example:

- Extracted `city` from the `location` field using a TRIM + FIND formula in Excel.
- Created 24 binary indicator columns, one per skill (Python, SQL, R, Spark, AWS, ...), using `=IF(ISNUMBER(SEARCH(...)),1,0)`.
- Pivoted the skill columns in Tableau to get a long-format table with `Skill` and `Mentioned`.
- Removed 17 rows that were duplicates or job-ad spam.

## 4. The 3 most surprising findings

1. **Finding 1** — short sentence with the number front and center.
2. **Finding 2** — short sentence with the number front and center.
3. **Finding 3** — the one a recruiter will quote.

## 5. The dashboard

Embed a screenshot here so the README looks good on GitHub:

```
![Week XX dashboard](dashboard.png)
```

And link to the live one:

**▶ Open the interactive dashboard:** <Tableau Public URL>

## 6. Tools used

- Apify (`<actor name>`)
- Microsoft Excel — pivots, formulas, light data cleaning
- Tableau Public Desktop — visualisation
- GitHub Desktop — version control

## 7. What I would do next

Two or three honest next steps. Example:

- Scrape another month of data and compare trends.
- Add salary information from Glassdoor to cross-reference.
- Build a small Python script to automate the scrape + clean step.

## 8. Reproduce this yourself

```bash
# 1. Clone the repo
git clone https://github.com/<yourusername>/data-science-portfolio.git
cd data-science-portfolio/week-XX-name

# 2. Re-run the scrape (needs an Apify account)
#    Open Apify Console → run actor "bebity/linkedin-jobs-scraper" with the input file:
#    apify-input.json

# 3. Open the cleaned workbook
open weekXX_clean.xlsx
```

## 9. Credits and contact

If you have feedback, ideas, or a job opening in mind I'd love to hear from you:
- LinkedIn: https://www.linkedin.com/in/pavethran-m/
- Email: pavethranmuthukumaran@gmail.com

If this was useful, star this repo — it helps me a lot when applying to roles.
