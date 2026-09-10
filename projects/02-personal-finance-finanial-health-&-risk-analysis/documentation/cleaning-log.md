# Cleaning Log — Personal Finance Financial Health & Risk Analysis

## Source
`synthetic_personal_finance_dataset.csv`

## Current status
Raw-data audit completed. No destructive filtering has been approved.

| Check | Result | Decision |
|---|---:|---|
| Rows | 32,424 | Retain |
| Columns | 20 | Retain |
| Full duplicate rows | 0 | No action |
| Duplicate user IDs | 0 | No action |
| Missing loan_type | 19,429 | Retain; consistent with has_loan = No |
| Negative income | 0 | No action |
| Negative expenses | 0 | No action |
| Negative savings | 0 | No action |
| Credit outside 300–850 | 0 | No action |
| No-loan records with loan amount | 0 | No action |
| No-loan records with EMI | 0 | No action |
| No-loan records with loan type | 0 | No action |
| Loan records with non-positive amount | 0 | No action |
| Loan records with non-positive EMI | 0 | No action |

## Ratio checks
DTI is consistent with `EMI ÷ monthly income`. Savings-to-income ratio is consistent with `savings ÷ (monthly income × 12)`.

## Previous filters — rejected
DTI > 2 and savings-to-income ratio > 1 are **not** automatic cleaning rules. Combined, the earlier rules would remove approximately 92% of observations and could create selection bias.

## Special review item
Ten loan holders have DTI recorded as exactly 0 despite positive loan/EMI values. Their values appear consistent with rounding at displayed precision. Review rather than delete.

## Current principle
**Clean structural errors; investigate unusual values; do not delete observations simply because they are extreme.**
