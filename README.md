# SaaS Cohort & Retention Analysis

Analysis of customer retention patterns for a simulated SaaS company, using SQL (DuckDB), Python, and Tableau to answer: **how well does the business retain customers over time, and why do they leave?**

🔗 **[Live Interactive Dashboard (Tableau Public)](https://public.tableau.com/app/profile/rishika.evenjalin/viz/SaaSCohortRetentionDashboard/SaaSCohortRetentionDashboard)**

## Tools Used
SQL (DuckDB) · Python (pandas, seaborn, matplotlib) · Jupyter Notebook · Tableau Public

## Project Structure


## Methodology
Cohorts were built from each account's *first subscription date* rather than their listed `signup_date` — investigation showed signup dates lagged real subscription activity by up to 14 months, making them unreliable as a cohort anchor. Similarly, the raw usage-event log proved temporally inconsistent with subscription windows in ~76% of records, so `churn_events` (a dedicated ground-truth table) was used to determine true retention instead.

## Key Findings
- Retention drops steeply in the first year (82% → ~40% by month 12), then levels off around 30-35% by month 20 — most churn risk is front-loaded into a customer's first year.
- Enterprise customers churn fastest of all tiers (avg. 4.4 months) versus Basic/Pro (5.5 months) — a red flag given Enterprise is typically the highest-value segment.
- Churn causes are evenly spread across missing features, budget, and support issues (each 15-19%) — no single fix solves most churn.
- DevTools and FinTech accounts churn at a noticeably higher rate than other industries.

## How to Reproduce
1. Clone this repo
2. `pip install duckdb pandas jupyter seaborn matplotlib`
3. Run `notebooks/01_cohort_analysis.ipynb` top to bottom

## Data Source
[SaaS Subscription & Churn Analytics Dataset](https://www.kaggle.com/datasets/rivalytics/saas-subscription-and-churn-analytics-dataset) (Kaggle, simulated data)

