# Dataset Catalog

## 1. Retail / E-commerce Sales Dataset

Used for **Project 01 — Retail Sales Data Cleaning**.

Known characteristics:
- Mixed date formats
- Quantity values stored as text and/or missing
- Price values stored as text and/or missing
- Inconsistent category capitalization
- Total sales calculated from quantity and price

## 2. Personal Finance ML Dataset

Used for **Project 02 — Personal Finance Dashboard**.

The source contains 32,424 rows and 20 columns. It is preserved in the project as raw data, with a separate cleaned/analysis layer. The current work focuses on financial-health analysis and an Excel dashboard.

### Important data-quality note

Some filtering decisions in the original project require further review before being presented as universal financial rules. In particular, extremely high DTI and savings-to-income values should be interpreted according to the dataset's definitions and business context rather than automatically treated as impossible.

The portfolio should preserve the distinction between:
- the original/raw data,
- documented transformation rules, and
- the analysis-ready data used by the dashboard.
