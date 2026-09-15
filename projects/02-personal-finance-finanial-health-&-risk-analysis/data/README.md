# Project 02 — Personal Finance Financial Health & Risk Analysis

## Objective
Analyze income, expenses, savings, debt and credit characteristics to determine what patterns may distinguish financially healthy, financially strained and potentially higher-risk individuals in a synthetic personal-finance dataset.

## Analytical question
> What financial characteristics distinguish financially healthy, financially strained, and potentially higher-risk individuals?

## Current status
**KPI selection and Excel analysis-layer phase.** The financial-health framework has been validated and locked as a descriptive, dataset-relative framework. The executive KPI set has been selected, and the first Excel analysis section is complete. Dashboard construction follows the remaining analysis sections.

## Workflow
1. Business problem
2. Data understanding
3. Data-quality audit
4. Exploratory analysis
5. Identify meaningful analytical questions
6. Analyze
7. Select KPIs
8. Build dashboard
9. Communicate findings and recommendations

## Data layers
`RAW → CLEANED → ANALYSIS`

The raw source is preserved. Unusual observations are investigated before being excluded.

## Important analytical decisions
- DTI > 2 is not automatically treated as invalid.
- Savings-to-income ratio > 1 is not automatically treated as invalid.
- Blank loan type for people without loans is treated as structurally meaningful.
- Correlation is treated as association, not causation.
- Synthetic-data patterns are not presented as real-world population evidence.

## Exploration completed so far
The project has tested income against expense burden and savings efficiency, DTI against credit score, and several hidden high-burden/high-resilience combinations. The strongest emerging conclusion is that income alone does not adequately describe financial health.

## Current analytical framework
A provisional three-segment framework has been selected for testing:
- **Financially Resilient:** 0 exploratory financial-pressure indicators
- **Financially Pressured:** 1–2 exploratory financial-pressure indicators
- **Financially Vulnerable:** 3–4 exploratory financial-pressure indicators

The framework is **not an official credit-risk model**. Its thresholds are dataset-relative exploratory criteria.

## Executive KPI set
The selected executive KPIs are:
1. Total Individuals
2. Median Monthly Income
3. Median Monthly Surplus
4. Median Expense Ratio
5. Loan Penetration
6. Financially Vulnerable Rate

Supporting measures include median DTI, median credit score, median savings, median savings-to-income ratio, median loan amount, median monthly EMI, median interest rate, and segment shares.

## Current next step
Continue the Excel analysis layer with the remaining decision-relevant analyses, then construct the dashboard from the established measures. Do not add analyses merely because they are technically possible.


## Current Progress — Excel Analysis Layer

The provisional financial-health framework has been validated and locked for this project as a **descriptive, dataset-relative analytical framework**. The first Excel analysis section, **Financial Health Overview**, is now complete. It compares the three segments using population share, median income, expenses, surplus, expense ratio, savings, savings-to-income ratio, and loan penetration.

The analysis workbook currently contains the raw-data layer, cleaned/derived-data layer, and the completed first analysis section. Dashboard construction will follow the remaining analysis sections rather than precede them.

### Current Segment Summary
- **Financially Resilient:** 14,578 individuals; median surplus $1,992.67; median expense ratio 51.6%; median savings $312,099.61; loan penetration 35.5%.
- **Financially Pressured:** 15,933 individuals; median surplus $941.04; median expense ratio 69.0%; median savings $113,579.51; loan penetration 41.6%.
- **Financially Vulnerable:** 1,913 individuals; median surplus $445.72; median expense ratio 83.3%; median savings $45,458.84; loan penetration 62.5%.

These results strengthen the analytical case for retaining the three-segment framework, while the project continues to avoid presenting it as an official credit-risk model.
