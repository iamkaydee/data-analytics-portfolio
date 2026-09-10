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
