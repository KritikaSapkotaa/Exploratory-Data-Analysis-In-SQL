# Exploratory Data Analysis in SQL: Worldwide Company Layoffs

In this project, we explore worldwide company layoffs data in MySQL to uncover trends over time and identify the companies with the most layoffs.

## Overview

This is the second part of a two-step SQL project. The first step, [Data Cleaning in SQL](https://github.com/KritikaSapkotaa/Data-Cleaning-In-SQL), turns the raw layoffs data into a clean table called `layoffs_staging2`. This project runs exploratory queries on that cleaned table to find patterns in who was laid off, when, and at what kind of company.

## Dataset

The analysis uses the cleaned `layoffs_staging2` table, which has these columns:

| Column | Description |
|---|---|
| company | Company that did the layoff |
| location | City or region of the layoff |
| industry | Industry sector |
| total_laid_off | Number of employees laid off |
| percentage_laid_off | Share of the workforce laid off (1 means 100%) |
| date | Date of the layoff |
| stage | Funding stage of the company |
| country | Country |
| funds_raised_millions | Total funding raised, in USD millions |

## Analysis Performed

| Analysis | What it answers |
|---|---|
| Maximum values | What was the largest single layoff, and the highest percentage laid off? |
| Companies that shut down | Which companies laid off 100% of their staff, sorted by how much funding they had raised? |
| Layoffs by company | Which companies had the most layoffs in total? |
| Date range | What time period does the data cover? |
| Layoffs by funding stage | How were layoffs spread across company funding stages? |
| Monthly layoffs | How did layoffs change month by month? |
| Rolling total | How did layoffs build up over time, month after month? |
| Layoffs by company and year | How many layoffs did each company have in each year? |
| Top 5 companies per year | Which 5 companies had the most layoffs in each year? |

## SQL Techniques Used

- Aggregate functions: `SUM()`, `MAX()`, `MIN()` with `GROUP BY`
- Filtering and sorting: `WHERE`, `ORDER BY`
- Date functions: `SUBSTRING()` to extract the month and `YEAR()` to extract the year
- Common Table Expressions (CTEs), including multiple CTEs chained together
- Window functions: `SUM() OVER()` for the rolling total and `DENSE_RANK()` with `PARTITION BY` for yearly rankings

## Tools

- MySQL
- MySQL Workbench

## Files

- `Data Exploratory project.sql`: the full exploratory analysis script

## How to Run

1. Run the cleaning script from the [Data Cleaning in SQL](https://github.com/KritikaSapkotaa/Data-Cleaning-In-SQL) project to create the `layoffs_staging2` table.
2. Open `Data Exploratory project.sql` in MySQL Workbench.
3. Run the queries one at a time to see each result.

## What I Learned

- Building rolling totals with window functions
- Ranking records within groups using `DENSE_RANK()` and `PARTITION BY`
- Structuring multi-step analysis with chained CTEs
- Turning cleaned data into questions and answers that show real trends

## Possible Next Steps

- Break down layoffs by industry and country
- Visualize the monthly trend and yearly rankings in Power BI or Tableau
