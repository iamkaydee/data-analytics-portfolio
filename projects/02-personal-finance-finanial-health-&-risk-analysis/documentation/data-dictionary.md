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

The current analysis layer also contains:

| Derived field | Meaning / rule |
|---|---|
| monthly_surplus | monthly income − monthly expenses |
| expense_ratio | monthly expenses ÷ monthly income |
| high_expense_burden_flag | 1 when expense ratio > 74.97188473%; otherwise 0 |
| high_dti_flag | 1 when has_loan = Yes and DTI > 3.07; otherwise 0 |
| low_surplus_flag | 1 when monthly surplus < $752.55; otherwise 0 |
| low_savings_efficiency_flag | 1 when savings-to-income ratio < 2.58; otherwise 0 |
| pressure_count | Sum of the four pressure flags (0–4) |
| financial_health_segment | 0 pressures = Resilient; 1–2 = Pressured; 3–4 = Vulnerable |

The financial-health segment is a descriptive, dataset-relative analytical classification and is not an official credit-risk score or prediction model.
