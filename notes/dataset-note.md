# 📂 Dataset Notes

# 📂 Dataset Cleaning Log

## Dataset: Messy ecommerce Sales Data

**Source:** Kaggle - Messy ecommerce Sales Data 
**Original File:** `messy_ecommerce_sales_data.csv` 
**Cleaned File:** `ecommerce_sales_data_cleaned.xlsx`  
**Date Cleaned:** 23/08/2026

---

## 1. Date Column

### Issues Found
- Mixed date formats (`DD/MM/YYYY` vs `MM/DD/YYYY`)
- Inconsistent capitalization (lowercase, uppercase, mixed) in `Category`
- Text values like `"abc"` in date column

### Actions Taken
- Used **Filter** to identify discrepancies
- Used **Text to Columns** → DMY format to standardize
- Used **Proper([Cell_id])** to fix capitalization patterns
- Removed text values (e.g., `"abc"`) → left blank

### Result
- ✅ All dates now in consistent `DD/MM/YYYY` format
- ✅ No text values remain in date column

---

## 2. Category Column

### Issues Found
- Inconsistent capitalization (`electronics`, `ELECTRONICS`, `eLeCtRoNiCs`)

### Actions Taken
- Used `=PROPER()` function to standardize capitalization
- Copied → Pasted Values to make changes permanent


### Result
- ✅ All categories now consistently capitalized (e.g., `Electronics`)

---

## 3. Quantity Column

### Issues Found
- Mixed numbers and text (e.g., `10 units`, `Qty: 10`, `4a`)
- Missing values (blank cells)

### Actions Taken
- Used **Find & Replace** to remove text patterns (` units`, `Qty: `, etc.)
- Extracted numbers from mixed entries (e.g., `4a` → `4`)
- Replaced blank cells with `0` (interpreted as "no units sold")

### Result
- ✅ All quantity values are now clean numbers
- ✅ Missing values filled with `0`

---

## 4. Price Column

### Issues Found
- Mixed numbers and text (e.g., `$10.99`, `10.99 USD`, `abc`, `four hundred`)
- Missing values (blank cells)

### Actions Taken
- Used **Find & Replace** to remove symbols and text (`$`, `USD`, `price: `, etc.)
- Deleted text-only values (e.g., `abc`) → left blank
- Manually converted text numbers where needed (e.g., `four hundred` → `400`)
- Replaced blank cells with `0`

### Result
- ✅ All price values are now clean numbers
- ✅ Ready for calculations

---

## 5. Total Column

### Actions Taken
- Re-calcalculated `Total` column using formula: `= Quantity × Price`
- Applied formula to all rows

### Result
- ✅ Total column added and populated

---

## Final Summary

| Column | Original Issues | Cleaning Method | Final State |
|--------|----------------|-----------------|-------------|
| Date | Mixed formats, text values, case issues | Text to Columns, Find & Replace | ✅ Consistent dates |
| Category | Inconsistent capitalization | `=PROPER()` function | ✅ Standardized |
| Quantity | Text+numbers mixed, blanks | Find & Replace, filled blanks with 0 | ✅ Clean numbers |
| Price | Text+numbers mixed, blanks | Find & Replace, manual fixes | ✅ Clean numbers |
| Total | New column | Formula: Quantity × Price | ✅ Populated |

---

## Files Affected

- Original: `messy_ecommerce_sales_data.csv` or `ecommerce_sales_data_cleaned.xlsx`  
- Cleaned: `[filename]-cleaned.xlsx`


## Lessons Learned

- Always keep a raw version before cleaning
- Use **Filter** to find and isolate issues
- **Find & Replace** is faster than manual edits
- **PROPER()** function fixes capitalization in one step
- Blanks can be handled differently depending on the column

## Dataset: Messy ecommerce Sales Data

**Source:** Kaggle - Messy ecommerce Sales Data 
**Original File:** `messy_ecommerce_sales_data.csv` 
**Cleaned File:** `ecommerce_sales_data_cleaned.xlsx`  
**Date Cleaned:** 23/08/2026

## DTI Column - Mass Outlier Removal

### Issue Discovered
- Over 8,000 rows had DTI > 2 (up to 90)
- These values are unrealistic (DTI > 2 means debt > 200% of income)

### Action Taken
- Filtered dataset to keep only rows with DTI ≤ 2
- Copied cleaned data to new sheet
- Deleted original heavy sheet to improve performance

### Result
- **Rows removed:** 8,000+
- **Rows remaining:** 27,569 rows
- **DTI range now:** 0 to 1.99
- **File performance:** Significantly improved

### Why This Was the Right Call
- DTI > 2 is financially impossible in real-world scenarios
- Real credit risk analysis uses DTI up to ~1.5 max
- Removing these rows ensures accurate analysis

## Savings to Income Ratio - Outlier Handling

### Issue
- Values > 1 found (savings exceeds income)
- 25074 rows affected out of 27569 total (90.94 % of data)

### Action Taken
- [Choose one:]
  - ✅ Deleted rows with ratio > 1
  - ✅ Capped ratio at 1
  - ✅ Flagged as "Check"

### Rationale
- Savings > Income is impossible without outside income
- These values are treated as data errors

### Files Affected
- `personal_finance_cleaned.xlsx`

## Data Reduction Note (Important)

**Final Dataset Size:** 2,495 rows (reduced from 24569)

**Reason for Reduction:**
- The original dataset was synthetically generated and contained unrealistic financial relationships.
- Over 90% of rows had either:
  1. A Debt-to-Income ratio > 2 (financially impossible).
  2. Savings exceeding Income (only possible with outside wealth, not captured in this data).
- These rows were removed to ensure the dashboard reflects **realistic financial behavior**.

**Impact:**
- The dataset is now smaller but **highly accurate** for analysis.
- All dashboard metrics (averages, trends) now represent real-world scenarios.

## Final Data Quality Check

### Columns Checked
| Column | Issue Found | Action Taken |
|--------|-------------|--------------|
| age | None | ✅ OK |
| gender | None | ✅ OK |
| education_level | None | ✅ OK |
| employment_status | None | ✅ OK |
| region | None | ✅ OK |
| monthly_income_usd | None | ✅ OK |
| monthly_expenses_usd | None | ✅ OK |
| savings_usd | None | ✅ OK |
| savings_to_income_ratio | None | ✅ OK |
| has_loan | None | ✅ OK |
| loan_type | None | ✅ OK |
| loan_amount_usd | None | ✅ OK |
| loan_term_months | None | ✅ OK |
| monthly_emi_usd | None | ✅ OK |
| loan_interest_rate_pct | None | ✅ OK |
| debt_to_income_ratio | Values > 2 removed | ✅ Fixed |
| credit_score | None | ✅ OK |
| record_date | None | ✅ OK |

### Final Decision
- All columns are clean and analysis-ready ✅
- Proceeding to dashboard creation
---