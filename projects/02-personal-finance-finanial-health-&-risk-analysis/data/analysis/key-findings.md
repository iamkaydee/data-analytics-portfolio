# Key Findings to Date

> **Exploratory only — not final business conclusions.**

1. The dataset contains 32,424 records and 20 columns, with no duplicate rows or duplicate user IDs.
2. The only missing field is `loan_type`; its 19,429 blanks correspond to no-loan records and are currently structurally consistent.
3. Earlier automatic filters for DTI > 2 and savings-to-income ratio > 1 were rejected; together they would remove about 92% of the data.
4. Monthly surplus is positive for every record; this may reflect synthetic data generation and prevents analysis of negative recorded cash flow.
5. Expense Ratio is tightly structured between approximately 30% and 90%, with median near 60%.
6. Higher income groups have higher absolute surplus, while expense ratio remains near 60% across income quartiles.
7. Region, employment status and age bands show relatively similar financial profiles so far.
8. Loan categories are broadly similar, although loan economics differ somewhat.
9. Credit score has extremely weak linear associations with other financial variables in this dataset.
10. Several variables are mathematically linked, so correlations must be interpreted with care.
11. The synthetic dataset shows unusually uniform/mechanical patterns that should be acknowledged when communicating findings.

## Current priority
The financial-health framework is validated and locked. The current priority is completing the KPI-driven Excel analysis layer before dashboard construction.

12. Income quartile analysis shows that median surplus rises from about $544 in Q1 to $2,537 in Q4, while median expense ratio remains approximately 60% across all income quartiles.
13. Savings balances increase substantially across income quartiles, but the median savings-to-income ratio remains close to 5, showing that absolute savings and savings efficiency tell different stories.
14. DTI and credit score show essentially no linear association in this dataset (Pearson r ≈ +0.012 overall; ≈ +0.015 among loan holders), so this relationship should not be treated as a major business finding.
15. Among the highest-income quartile, 2,029 of 8,106 individuals (25.0%) have expense ratios above approximately 75%, demonstrating that high income does not automatically imply low relative expense burden.
16. Seventy-seven records meet all three exploratory conditions of high income, expense ratio above ~75%, and DTI above ~3.07. These are **potential high-burden profiles**, not confirmed financial-risk cases.
17. Among the lowest-income quartile, 2,032 of 8,106 individuals (25.1%) have savings-to-income ratios above ~7.51. This demonstrates that low income does not automatically imply weak savings efficiency.
18. The hidden-pattern analyses strengthen the case for multidimensional financial-health assessment rather than a single-variable income or risk classification.

13. Savings balances increase substantially across income quartiles, but the median savings-to-income ratio remains close to 5, showing that absolute savings and savings efficiency tell different stories.
14. DTI and credit score show essentially no linear association in this dataset (Pearson r ≈ +0.012 overall; ≈ +0.015 among loan holders), so this relationship should not be treated as a major business finding.
15. Among the highest-income quartile, 2,029 of 8,106 individuals (25.0%) have expense ratios above approximately 75%, demonstrating that high income does not automatically imply low relative expense burden.
16. Seventy-seven records meet all three exploratory conditions of high income, expense ratio above ~75%, and DTI above ~3.07. These are **potential high-burden profiles**, not confirmed financial-risk cases.
17. Among the lowest-income quartile, 2,032 of 8,106 individuals (25.1%) have savings-to-income ratios above ~7.51. This demonstrates that low income does not automatically imply weak savings efficiency.
18. The hidden-pattern analyses strengthen the case for multidimensional financial-health assessment rather than a single-variable income or risk classification.

19. Four exploratory financial-pressure indicators were combined into a pressure count: high expense burden, high DTI, low surplus and low savings efficiency.
20. 7,629 records (23.5%) have at least two pressure indicators, and 1,913 (5.9%) have at least three.
21. Median surplus falls from about $1,993 for records with zero pressures to about $350 for records with four pressures, while loan penetration rises from 35.5% to 100%.
22. The pressure-count pattern supports a provisional three-segment framework: Financially Resilient (0), Financially Pressured (1–2), and Financially Vulnerable (3–4). This is descriptive and dataset-relative, not an official risk model.
23. Segment profiles are clearly differentiated: Resilient (14,578 records) has median surplus ≈$1,993; Pressured (15,933) ≈$941; Vulnerable (1,913) ≈$446.
24. Credit score remains a supporting variable rather than a segmentation driver because its relationships with the other financial variables are extremely weak in this synthetic dataset.

## Finding 25 — Financial-health segments show a strong surplus gradient
Median monthly surplus falls from **$1,992.67** in the Financially Resilient segment to **$941.04** in the Financially Pressured segment and **$445.72** in the Financially Vulnerable segment.

**Implication:** the segmentation corresponds to materially different levels of monthly financial capacity.

## Finding 26 — Expense burden rises sharply across segments
Median expense ratio rises from **51.6%** (Resilient) to **69.0%** (Pressured) and **83.3%** (Vulnerable).

**Implication:** relative spending burden is a strong supporting characteristic of the segment structure.

## Finding 27 — Savings decline substantially across segments
Median savings falls from **$312,099.61** (Resilient) to **$113,579.51** (Pressured) and **$45,458.84** (Vulnerable). Median savings-to-income ratio also falls from **6.29** to **3.57** to **1.76**.

**Implication:** both absolute savings and savings relative to annual income distinguish the segments.

## Finding 28 — Loan exposure is highest in the Vulnerable segment
Loan penetration rises from **35.5%** in the Resilient segment to **41.6%** in the Pressured segment and **62.5%** in the Vulnerable segment.

**Implication:** the Vulnerable group combines higher financial pressure with substantially greater loan exposure.

## Finding 29 — Excel analysis layer is now established
The first analysis section, **Financial Health Overview**, has been built in the project workbook using segment-level counts and median-based measures. This establishes the core analytical table before dashboard construction.


## Finding 30 — The executive KPI set is now defined
Six executive KPIs have been selected: **Total Individuals, Median Monthly Income, Median Monthly Surplus, Median Expense Ratio, Loan Penetration, and Financially Vulnerable Rate**. Supporting measures will provide detail without overcrowding the executive view.

## Finding 31 — The first Excel analysis section provides the core segment comparison
The completed **Financial Health Overview** compares the three segments using population share, median income, expenses, surplus, expense ratio, savings, savings-to-income ratio and loan penetration. The measures show a consistent gradient from Resilient to Vulnerable and provide the analytical basis for subsequent dashboard visuals.
