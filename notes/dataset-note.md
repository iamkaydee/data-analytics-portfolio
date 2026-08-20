# 📂 Dataset Notes

## Retail Sales Dataset

**Source:** Kaggle - "US Retail Sales Dataset"
**Downloaded:** Aug 20, 2026
**File Name:** `retail-sales.csv`

### Original Columns
| Column | Description |
|--------|-------------|
| `Order_Date` | Date of sale |
| `Region` | US region (South, East, West, North) |
| `Product` | Product name |
| `Sales` | Sales amount ($) |
| `Units_Sold` | Quantity sold |

### Data Quality Issues Found
- ❌ 50 rows with missing `Region` → Removed
- ❌ 25 rows with negative `Sales` → Investigated (returns?) → Kept with note
- ❌ `Order_Date` was text format → Converted to date
- ❌ Duplicate rows (25 found) → Removed duplicates

### Cleaned File
**File Name:** `retail-sales-cleaned.xlsx`
**Location:** `/projects/retail-sales-cleaned.xlsx`

### Analysis Done
- 📊 Pivot table: Sales by Region
- 📈 Chart: Monthly sales trend
- 🔢 Formulas added: Total Sales, Average Order Value

---