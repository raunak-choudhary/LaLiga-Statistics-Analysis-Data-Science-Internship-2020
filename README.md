# LaLiga Statistics Analysis

An analysis of 61 clubs that have played in Spain's top football division, cleaning the historical record into computable form and deriving performance metrics that rank teams across their entire history in the competition.

This is **Mini Project 3 of 3** completed during a Data Science internship at Great Learning Pvt. Ltd., 15 June to 16 August 2020.

## Overview

The dataset is a career summary rather than a match log: one row per club, covering every season that club has ever played in LaLiga. That structure makes it suited to cumulative questions. Who has accumulated the most points across all time, who has the best scoring record relative to goals conceded, and which clubs convert appearances into wins most efficiently.

The raw file is not immediately computable. Clubs that never reached a given position carry a dash rather than a zero, so entire columns arrive as text and arithmetic fails until they are cleaned. Getting from that to a ranked table is most of the work.

The task list and point allocation come from `Project Description Stats.pdf`, included in the repository.

## Dataset

`Laliga.csv`, **61 rows across 20 columns**, one row per club.

Columns include `Team`, `Debut`, `Seasons`, `Points`, `GamesPlayed`, `GamesWon`, `GamesDrawn`, `GamesLost`, `GoalsFor`, `GoalsAgainst`, `BestPosition`, and per-position finish counts from `Champion` and `Runner-up` through to `Sixth`.

## Approach

**Cleaning.** Dashes marking "never achieved" are replaced with zero across the frame, then the affected columns are cast from object to integer so arithmetic becomes possible. This is the step everything else depends on.

**Filtering.** Debut years are treated as strings and sliced to isolate the year, allowing clubs that entered the league between 1930 and 1980 inclusive to be selected.

**Derived metrics.** Two new measures are computed:

- **Goal difference**, as `GoalsFor - GoalsAgainst`, wrapped in a reusable function so it can be recomputed and reused rather than inlined once
- **Winning percentage**, as `(GamesWon / GamesPlayed) * 100`, appended as a new column with division errors filled to zero so clubs with no recorded games do not propagate NaN

**Aggregation.** Clubs are grouped by their best-ever finishing position and their points summed within each group, showing how total accumulated points distribute across achievement tiers.

## Results

**Top five clubs by total points**

| Club | Points |
| --- | --- |
| Real Madrid | 4,385 |
| Barcelona | 4,262 |
| Atletico Madrid | 3,442 |
| Valencia | 3,386 |
| Athletic Bilbao | 3,368 |

**Top five clubs by winning percentage**

| Club | Win % |
| --- | --- |
| Real Madrid | 59.63 |
| Barcelona | 57.24 |
| Atletico Madrid | 47.48 |
| Valencia | 44.56 |
| Athletic Bilbao | 43.77 |

The two rankings return the same five clubs in the same order, which is itself a finding. Total points reward longevity and winning percentage rewards efficiency, and a club topping both is dominant on volume and on rate simultaneously rather than merely long-lived.

The gap is also informative: Real Madrid and Barcelona sit above 57 percent while third place falls to 47, a gulf far wider than the one separating third from fifth.

**Goal difference extremes**

- Best: **Real Madrid**, +2,807
- Worst: **Racing Santander**, -525

**Points by best-ever position.** Grouping by highest position ever achieved and summing points across each group:

| Best position | Total points |
| --- | --- |
| 1 | 27,933 |
| 2 | 6,904 |
| 4 | 6,563 |
| 3 | 5,221 |
| 6 | 2,113 |
| 5 | 1,884 |
| 7 | 1,186 |
| 8 | 1,134 |
| 12 | 511 |
| 10 | 450 |
| 11 | 445 |
| 9 | 96 |
| 14 | 71 |

Clubs that have won the title at least once account for roughly 27,933 points, more than the other twelve groups combined. That concentration reflects a small set of clubs appearing in nearly every season while most others pass through briefly.

## Scope Note

This project is descriptive rather than inferential. It covers cleaning, derived metrics, ranking, and grouped aggregation, with no hypothesis testing or significance testing. The inferential work from this internship lives in the Insurance Cost project linked below.

## Tech Stack

- Python 3
- Jupyter Notebook
- pandas
- NumPy

## Running It

```bash
pip install pandas numpy jupyter
jupyter notebook "Mini Project 3 - Applied Statistics on LaLiga Dataset_Submission_Raunak_Choudhary.ipynb"
```

The dataset is included, so the notebook runs top to bottom without additional setup. HTML and PDF exports of the completed notebook are also committed.

## Internship Series

This is one of three projects from the same internship:

1. [Amazon Ecommerce Purchase Analysis](https://github.com/raunak-choudhary/Amazon-Ecommerce-Purchase-Analysis-Data-Science-Internship-2020): pandas querying and filtering
2. [Insurance Cost Statistical Analysis](https://github.com/raunak-choudhary/Insurance-Cost-Statistical-Analysis-Data-Science-Internship-2020): EDA plus hypothesis testing with t-tests, chi-square, and ANOVA
3. **LaLiga Statistics Analysis** (this repository): data cleaning, derived metrics, and grouped aggregation

## Author

**Raunak Choudhary**

Data Science Intern, Great Learning Pvt. Ltd.

[Email](mailto:raunakchoudhary17@gmail.com) · [LinkedIn](https://www.linkedin.com/in/raunak-choudhary)
