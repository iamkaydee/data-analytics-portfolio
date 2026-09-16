# Methodology — Personal Finance Financial Health & Risk Analysis

## Analytical philosophy
**Business problem → Data understanding → Data-quality audit → Exploration → Analytical questions → Analysis → KPI selection → Dashboard → Recommendations**.

The dashboard is the communication layer, not the starting point.

## Data layers
**RAW → CLEANED → ANALYSIS**

RAW remains untouched. CLEANED handles structural preparation. ANALYSIS contains derived variables and analytical flags. Analytical filtering must not overwrite RAW.

## Missing loan type
Blank `loan_type` values correspond to `has_loan = No` and are treated as structurally meaningful rather than automatically imputed.

## Extreme ratios
DTI is approximately `monthly EMI / monthly income`; values above 2 are extreme but not automatically invalid. Savings-to-income ratio is approximately `savings / (monthly income × 12)`; values above 1 are not automatically invalid. Earlier deletion rules were rejected because they would remove about 92% of observations and could introduce selection bias.

## Derived metrics
**Monthly Surplus** = monthly income − monthly expenses.

**Expense Ratio** = monthly expenses ÷ monthly income. For this project, this means the share of monthly income represented by monthly expenses; it is not investment-fund expense-ratio terminology.

## Descriptive statistics
**Mean:** arithmetic average = sum of values ÷ number of observations; sensitive to extreme values.

**Median:** middle observation after sorting; with an even count, the average of the two middle observations.

**Percentile:** value at or below which a specified percentage of observations fall.

**Quartile:** division of ordered observations into four approximately equal groups.

## Correlation
Pearson correlation measures linear association between numerical variables from -1 to +1. It does not establish causation. Because several fields are mathematically derived from others, correlation must be interpreted in context.

## Interpretation protocol
For important results, separate:
1. **Observation** — what the data directly shows.
2. **Interpretation** — a reasonable meaning or explanation.
3. **Limitation** — what the evidence does not establish.
4. **Decision** — whether the result matters to the project.

## Financial-health segmentation
A **descriptive, dataset-relative segmentation** is approved and locked for the portfolio after exploratory testing and sensitivity review. It uses four indicators: high expense burden, high DTI, low surplus and low savings efficiency. Each record receives a pressure count from 0–4, then is grouped as:
- **Financially Resilient:** 0 pressures
- **Financially Pressured:** 1–2 pressures
- **Financially Vulnerable:** 3–4 pressures

This segmentation is not an official credit-risk model, prediction model, or domain-certified financial-health score. The thresholds are relative to this dataset and are intended to communicate patterns consistently. Credit score is not a segmentation driver because it shows almost no linear relationship with the other financial variables in this dataset.

### Locked exploratory thresholds
- High expense burden: expense ratio > **74.97188473%** (dataset 75th percentile).
- High DTI: DTI > **3.07** among loan holders (dataset 75th percentile).
- Low surplus: monthly surplus < **$752.55** (dataset 25th percentile).
- Low savings efficiency: savings-to-income ratio < **2.58** (dataset 25th percentile).

The exact thresholds are retained in the Excel formulas so that the segment counts reproduce the validated totals of 14,578 Resilient, 15,933 Pressured and 1,913 Vulnerable records.

## Scope control
Analyses must contribute to the central question, reveal a meaningful pattern, test an important assumption, validate data quality, or improve KPI/dashboard/recommendation decisions.

## Exploratory segmentation criteria
Quartiles and percentiles are used as **distribution-based exploratory criteria**, not as official financial-risk thresholds. A quartile divides ordered observations into four approximately equal groups. A percentile identifies a position within an ordered distribution (for example, the 75th percentile). These methods may be useful for exploration, but they should not automatically be interpreted as domain-defined risk categories.

For hidden-pattern analysis, Q4 income represents the highest 25% of income observations; an expense ratio above its 75th percentile (approximately 75%) represents relatively high expense burden; DTI above approximately 3.07 represents relatively high DTI in the exploratory distribution used; and a savings-to-income ratio above approximately 7.51 represents relatively high savings efficiency within the dataset. These are deliberately labelled **exploratory relative thresholds**.

The hidden-pattern findings show that high income can coexist with high expense burden and high DTI, while low income can coexist with relatively strong savings efficiency. Therefore, final financial-health segmentation should combine multiple dimensions and should not label individuals as financially healthy or risky using any one exploratory threshold.

## Excel Analysis Layer Method

The first Excel analysis section groups records by the provisional Financial Health Segment and calculates **median-based** summary measures. Median is used for financial amounts and ratios because it represents the middle observation and is less sensitive to extreme values than the arithmetic mean.

The first section includes population size, population share, median income, median expenses, median monthly surplus, median expense ratio, median savings, median savings-to-income ratio, and loan penetration.

This section is intentionally completed before dashboard design so that visualizations are based on established analytical measures rather than chosen for appearance first.
