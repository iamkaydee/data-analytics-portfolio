# Project 02 — Personal Finance Financial Health & Risk Analysis

## Objective
Analyze income, expenses, savings, debt and credit characteristics to determine what patterns may distinguish financially healthy, financially strained and potentially higher-risk individuals in a synthetic personal-finance dataset.

## Analytical question
> What financial characteristics distinguish financially healthy, financially strained, and potentially higher-risk individuals?

## Current status
**Exploration-to-framework phase.** Exploratory testing is complete enough to define a provisional financial-health framework. Final KPIs and dashboard layout are still pending.

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

## Current next step
Finalize the KPI set and build the Excel analysis layer using the approved framework. Then construct the dashboard. The project will not calculate every possible combination merely because it is technically possible.
