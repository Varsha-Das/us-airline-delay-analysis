# US Airline Delay Analysis: Six Sigma DMAIC on BTS 2024

A full-year **Six Sigma DMAIC** study of US domestic flight delays, run on **6.97 million flights** across 15 carriers and 348 airports. It measures how often flights are late, finds the root causes and builds models that point to specific fixes.

**Course:** Modelling in Operations Management (MIOM), PGDBA  
**Team (Group 10):** Shiwam Birajdar, Boddu Harsha, Harshini Reddy P, Jaganatha Pandiyan, Srirang Nabar, Varsha Das  
📄 [Full report](docs/Report.pdf)

## Key findings
- **Baseline:** 19.94 % of flights leave more than 15 minutes late (DPMO 199,402, **2.34σ**). Every carrier is below 3σ and has Cpk under 0.1, so this is an industry-wide problem rather than one airline's.
- **Pareto:** 6 of 15 airlines account for about 75 % of delayed departures, and Southwest alone for 22.6 %.
- **Root cause:** **74.9 % of delay minutes are controllable.** Late inbound aircraft cause 40.4 % and carrier issues 34.5 %. Departure delay predicts arrival delay almost perfectly (r = 0.971).
- **Hypothesis tests:** ANOVA across airlines (F = 2,854.7) and Kruskal-Wallis across days (H = 28,168) and months (H = 147,540) are all significant at p < 0.0001. July averages 22.2 minutes of delay and October 5.4.
- **Modelling:** an OLS model on the cascaded-delay subgroup reaches **R² 0.704**, against 0.487 on all flights. A Z-test (z = −13.37) confirms that late planes behave differently.
- **Segmentation:** K-Means (k = 3) on carrier fixed effects sorts airlines into *High Performers*, *Structurally Poor* and *Cascade-Prone* groups. This gives a matrix of targeted fixes for each group.

## Repository
```
Analysis.ipynb                          # full DMAIC pipeline
data/flight_data_2024_sample.csv        # sample of the BTS dataset
data/flight_data_2024_data_dictionary.csv
docs/Report.pdf
```
> The full 7M-row 2024 dataset is too large for GitHub. Download it from the [BTS On-Time Performance](https://www.transtats.bts.gov/) portal.

## Tech
Python · pandas · SciPy · statsmodels · scikit-learn · Matplotlib · Seaborn
