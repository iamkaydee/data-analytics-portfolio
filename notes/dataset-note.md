# 📂 Dataset Notes

# 📂 Dataset Cleaning Log

## Dataset: [Your Dataset Name, e.g., Retail Sales Data]

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