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

For every analysis: state what is being tested, why it matters, how it is calculated, what the data shows, what can/cannot be inferred, and whether it deserves to remain in the final project.

## Scope guardrail
Do not calculate every possible cross-tabulation. An analysis must help answer the financial-health question, reveal a meaningful pattern, test an important assumption, validate data quality, or improve KPI/dashboard/recommendation decisions.

## Analysis 1 — Income × Expense Ratio
Question: Does higher income change the proportion of income represented by monthly expenses?

Method: Monthly income was divided into four **income quartiles** (8,106 records each). Quartiles are distribution-based groups: Q1 is the lowest 25%, Q2 the next 25%, Q3 the next 25%, and Q4 the highest 25%. Expense Ratio = monthly expenses ÷ monthly income.

| Income quartile | Median income | Median expense ratio | Median surplus |
|---|---:|---:|---:|
| Q1 | $1,709.69 | ~60.1% | $544.20 |
| Q2 | $3,361.68 | ~60.0% | $1,322.68 |
| Q3 | $4,635.73 | ~60.0% | $1,850.48 |
| Q4 | $6,273.46 | ~60.1% | $2,536.83 |

Observation: Higher-income groups have substantially higher absolute surplus, while expense ratio remains approximately 60% across all four quartiles.

Interpretation: Higher income increases absolute financial capacity in this dataset, but does not appear to reduce the proportional expense burden.

Limitation: The unusually stable expense ratio may reflect the synthetic data-generation process rather than real-world spending behaviour.

Decision: **KEEP** as a useful financial-health analysis and dashboard story.

## Analysis 2 — Income × Savings-to-Income Ratio
Question: As income increases, do people save a larger proportion of income, or simply accumulate larger savings balances?

Savings-to-income ratio = savings ÷ (monthly income × 12).

| Income quartile | Median income | Median savings | Median savings-to-income ratio |
|---|---:|---:|---:|
| Q1 | $1,709.69 | $77,107.83 | 5.03 |
| Q2 | $3,361.68 | $198,497.26 | 5.01 |
| Q3 | $4,635.73 | $284,350.36 | 5.10 |
| Q4 | $6,273.46 | $381,829.07 | 5.02 |

Observation: Savings balances rise strongly with income, but the savings-to-income ratio remains close to 5 across income quartiles.

Interpretation: Higher income is associated with greater savings in absolute dollars, but not with a materially higher savings-to-income ratio in this dataset.

Limitation: The highly stable ratio may be a synthetic-data construction.

Decision: **KEEP**, particularly as evidence that absolute balances and financial ratios tell different stories.

## Analysis 3 — DTI × Credit Score
Question: Does higher debt burden appear to be associated with lower credit scores?

Pearson correlation is approximately +0.012 for the full dataset and +0.015 among loan holders. This is essentially zero linear association.

Exploratory DTI quartiles among loan holders also show no consistent credit-score pattern; median credit scores remain around the mid-to-high 500s across DTI groups.

Observation: Credit scores do not vary systematically with DTI in this dataset.

Interpretation: DTI does not appear to distinguish credit scores here.

Limitation: This is descriptive correlation, not a formal significance test; correlation does not establish causation.

Decision: **KEEP as a tested assumption/dataset-quality insight, but do not make it a major business finding.**

## Analysis 4 — Hidden Risk: High Income + High Expense Burden + High DTI
Question: Can people with high income still have relatively high financial burden?

Exploratory thresholds were distribution-based rather than official risk thresholds:
- High income = Q4 income (top 25%).
- High expense burden = expense ratio above its 75th percentile, approximately 75%.
- High DTI = DTI above its 75th percentile among the relevant exploratory distribution, approximately 3.07.

Among 8,106 Q4-income individuals, 2,029 (25.0%) have expense ratios above ~75%.

Among high-income loan holders, 276 are simultaneously above the exploratory high-DTI threshold. Across the full dataset, 77 records meet all three exploratory conditions: high income, high expense ratio and high DTI.

Observation: High income does not automatically imply low relative financial burden.

Interpretation: A multidimensional financial-health view is more informative than income alone.

Limitation: These quartile/percentile thresholds are exploratory relative thresholds, not official definitions of financial risk. The 77 records should not be labelled financially risky solely on this basis.

Decision: **KEEP as a core analytical insight.**

## Analysis 5 — Hidden Resilience: Low Income + Strong Savings Efficiency
Question: Can people in the lowest income group nevertheless show relatively strong savings behaviour?

Method: Q1 income identifies the lowest 25% of earners. The 75th percentile of savings-to-income ratio is approximately 7.51. This is an exploratory relative threshold, not an official savings benchmark.

Among 8,106 Q1-income individuals, 2,032 (25.1%) have savings-to-income ratios above 7.51.

Observation: A meaningful subset of the lowest-income group has relatively high savings-to-income ratios.

Interpretation: Income alone can also fail to identify potentially resilient financial profiles; financial-health assessment should consider savings behaviour alongside income.

Limitation: Savings-to-income ratio above 7.51 is a dataset-relative criterion. It does not establish that these individuals are financially healthy in the real world.

Decision: **KEEP**, but use it to support multidimensional segmentation rather than to create a risk label.

## Analytical direction after hidden-pattern testing
The analyses support a multidimensional financial-health framework involving income capacity, expense burden, surplus, savings/reserves and debt burden. Credit score appears less useful for differentiation in this particular synthetic dataset.

No final financial-health classification or `High_Risk` flag has yet been approved. The next methodological task is to define defensible thresholds/segments before building the final KPI set and dashboard.
