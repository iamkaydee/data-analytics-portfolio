# Personal Finance Financial Health & Risk Analysis — Analysis Notes

## Objective
> What financial characteristics distinguish financially healthy, financially strained, and potentially higher-risk individuals in this dataset?

Workflow: **Business problem → data understanding → data-quality audit → exploration → analytical questions → analysis → KPI selection → dashboard → recommendations**.

Current stage: **exploration / identification of meaningful analytical questions**.

## Dataset
- 32,424 records × 20 columns
- Synthetic personal-finance data
- Unique user IDs; no duplicate IDs
- No full duplicate rows
- Actual CSV record dates: 2021-07-23 to 2025-07-22

## Data-quality audit
The only missing field is `loan_type` (19,429 records), and those blanks correspond to `has_loan = No`. This is treated as structurally consistent.

No negative income, expenses, savings, DTI or savings-to-income ratios were found. Credit scores fall within 300–850. Loan consistency checks found no cases of no-loan records carrying loan amounts/EMI/type or loan records having non-positive amounts/EMI.

## Revision to earlier cleaning assumptions
### DTI > 2
Earlier automatic deletion was rejected. In this dataset DTI is essentially `monthly EMI / monthly income`. A value above 2 is extreme, but extreme does not automatically mean invalid. 4,837 records (14.92%) have DTI > 2. Retain pending defensible business/source criteria.

### Savings-to-income ratio > 1
Earlier automatic deletion was rejected. The ratio is essentially `savings / (monthly income × 12)`. A value above 1 can occur when accumulated savings exceed one year's current income. 29,465 records (90.87%) have a ratio > 1. Retain pending defensible criteria.

Applying either old rule would remove about 92% of the dataset and risks selection bias.

## Derived measures
### Monthly Surplus
`Monthly Income − Monthly Expenses`
Median ≈ $1,385.82; mean ≈ $1,608.42; min ≈ $50.56; max ≈ $7,158.31. There are **0 negative-surplus records**.

### Expense Ratio
For this project: `Monthly Expenses / Monthly Income`. Example: $2,400 / $4,000 = 60%. This is a project-defined metric and should not be confused with investment-fund expense-ratio terminology.

Observed range ≈ 30%–90%; median ≈ 60%.

## Exploration
Income quartiles contain 8,106 records each:

| Quartile | Median income | Median surplus |
|---|---:|---:|
| Q1 | $1,709.69 | $544.20 |
| Q2 | $3,361.68 | $1,322.68 |
| Q3 | $4,635.73 | $1,850.48 |
| Q4 | $6,273.46 | $2,536.83 |

Higher income is associated with higher absolute surplus, while expense ratio remains around 60% across quartiles.

Region, employment status and age bands show broadly similar profiles in the outcomes examined so far. Loan categories are also broadly similar, although loan economics differ somewhat.

## Credit score
Credit score shows extremely weak linear associations with most financial variables in this dataset. This is a descriptive correlation finding, not a formal test of statistical significance and not evidence that credit score is generally unimportant.

## Selected correlations
- Income ↔ Expenses: 0.829
- Income ↔ Surplus: 0.702
- Income ↔ Savings: 0.604
- Loan amount ↔ EMI: 0.720
- DTI ↔ EMI: 0.661
- Savings ↔ savings-to-income ratio: 0.719
- Surplus ↔ Expense Ratio: -0.641
- DTI ↔ loan amount: 0.481
- DTI ↔ interest rate: 0.373
- Income ↔ DTI: -0.238

Pearson correlation measures linear association from -1 to +1; it does not establish causation. Some strong relationships are mathematical because variables are derived from one another.

## Synthetic-data observations
Expense ratio is tightly structured; all surpluses are positive; credit score is nearly independent of other financial variables; regional/employment/age profiles are similar; loan categories are similar; and several ratios are mathematically consistent with source fields. These may reflect the synthetic data-generation process rather than real-world behaviour.

## Current analytical direction
Explore financial health as a multidimensional concept involving:
1. Income capacity
2. Expense burden
3. Debt burden
4. Financial reserves
5. Credit profile

No final financial-health classification or `High_Risk` flag has been approved.

## Next step: hidden patterns
Investigate combinations such as:
- Income × Expense Ratio
- Income × Surplus
- Income × Savings
- DTI × Income
- DTI × Savings
- DTI × Credit Score
- Expense Ratio × Savings
- Expense Ratio × DTI