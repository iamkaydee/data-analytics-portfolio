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
Investigate combinations of income, expense burden, surplus, savings, debt burden and credit profile before defining financial-health segments or final KPIs.

12. Income quartile analysis shows that median surplus rises from about $544 in Q1 to $2,537 in Q4, while median expense ratio remains approximately 60% across all income quartiles.
13. Savings balances increase substantially across income quartiles, but the median savings-to-income ratio remains close to 5, showing that absolute savings and savings efficiency tell different stories.
14. DTI and credit score show essentially no linear association in this dataset (Pearson r ≈ +0.012 overall; ≈ +0.015 among loan holders), so this relationship should not be treated as a major business finding.
15. Among the highest-income quartile, 2,029 of 8,106 individuals (25.0%) have expense ratios above approximately 75%, demonstrating that high income does not automatically imply low relative expense burden.
16. Seventy-seven records meet all three exploratory conditions of high income, expense ratio above ~75%, and DTI above ~3.07. These are **potential high-burden profiles**, not confirmed financial-risk cases.
17. Among the lowest-income quartile, 2,032 of 8,106 individuals (25.1%) have savings-to-income ratios above ~7.51. This demonstrates that low income does not automatically imply weak savings efficiency.
18. The hidden-pattern analyses strengthen the case for multidimensional financial-health assessment rather than a single-variable income or risk classification.

12. Income quartile analysis shows that median surplus rises from about $544 in Q1 to $2,537 in Q4, while median expense ratio remains approximately 60% across all income quartiles.
13. Savings balances increase substantially across income quartiles, but the median savings-to-income ratio remains close to 5, showing that absolute savings and savings efficiency tell different stories.
14. DTI and credit score show essentially no linear association in this dataset (Pearson r ≈ +0.012 overall; ≈ +0.015 among loan holders), so this relationship should not be treated as a major business finding.
15. Among the highest-income quartile, 2,029 of 8,106 individuals (25.0%) have expense ratios above approximately 75%, demonstrating that high income does not automatically imply low relative expense burden.
16. Seventy-seven records meet all three exploratory conditions of high income, expense ratio above ~75%, and DTI above ~3.07. These are **potential high-burden profiles**, not confirmed financial-risk cases.
17. Among the lowest-income quartile, 2,032 of 8,106 individuals (25.1%) have savings-to-income ratios above ~7.51. This demonstrates that low income does not automatically imply weak savings efficiency.
18. The hidden-pattern analyses strengthen the case for multidimensional financial-health assessment rather than a single-variable income or risk classification.
