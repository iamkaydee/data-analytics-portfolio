# Data Dictionary — Personal Finance Financial Health & Risk Analysis

| Field | Meaning / project use |
|---|---|
| user_id | Unique identifier for each record |
| age | Age in years |
| gender | Recorded gender category |
| education_level | Recorded education category |
| employment_status | Employment category |
| job_title | Recorded job title |
| monthly_income_usd | Monthly income in USD |
| monthly_expenses_usd | Monthly expenses in USD |
| savings_usd | Recorded savings balance in USD |
| has_loan | Whether the individual has a loan |
| loan_type | Loan category; blank when no loan is held |
| loan_amount_usd | Loan amount in USD |
| loan_term_months | Loan term in months |
| monthly_emi_usd | Monthly loan repayment amount in USD |
| loan_interest_rate_pct | Loan interest rate percentage |
| debt_to_income_ratio | Debt burden ratio; approximately EMI ÷ monthly income in this dataset |
| credit_score | Recorded credit score |
| savings_to_income_ratio | Approximately savings ÷ (monthly income × 12) |
| region | Recorded geographic region |
| record_date | Date associated with the record |

## Project-derived fields
**Monthly Surplus** = monthly income − monthly expenses.

**Expense Ratio** = monthly expenses ÷ monthly income. In this project it means the proportion of monthly income represented by monthly expenses.

Potential future fields such as income bands, DTI bands, risk flags and financial-health segments remain under consideration and are not finalized.
