# Project 02 — Personal Finance Financial Health & Risk Analysis

## Objective
Analyze income, expenses, savings, debt and credit characteristics to determine what patterns may distinguish financially healthy, financially strained and potentially higher-risk individuals in a synthetic personal-finance dataset.

## Analytical question
> What financial characteristics distinguish financially healthy, financially strained, and potentially higher-risk individuals?

## Current status
**Exploration phase.** Financial-health definitions, final analytical questions and final KPIs have not yet been finalized.

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

## Current next step
Investigate hidden financial-health patterns across income, expense burden, surplus, savings, debt burden and credit profile. The project will not calculate every possible combination merely because it is technically possible.
