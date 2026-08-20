# 📊 Excel Cheatsheet

## Basic Formulas

| Formula | What It Does | Example |
|---------|--------------|---------|
| `=SUM(A1:A10)` | Adds up values | Total sales |
| `=AVERAGE(A1:A10)` | Average of values | Average price |
| `=COUNT(A1:A10)` | Counts numbers | Number of orders |
| `=COUNTA(A1:A10)` | Counts non-empty cells | Total records |
| `=MIN(A1:A10)` | Finds smallest value | Lowest sales day |
| `=MAX(A1:A10)` | Finds largest value | Highest sales day |

## Lookup Formulas

| Formula | What It Does |
|---------|--------------|
| `=VLOOKUP(value, table, column, FALSE)` | Find value in a table |
| `=XLOOKUP(value, lookup_array, return_array)` | Better version of VLOOKUP |

## If Statements

| Formula | What It Does |
|---------|--------------|
| `=IF(A1>100, "High", "Low")` | Returns "High" if A1 > 100 |

## Date Functions

| Formula | What It Does |
|---------|--------------|
| `=TODAY()` | Current date |
| `=YEAR(A1)` | Extracts year from date |
| `=MONTH(A1)` | Extracts month from date |

## Quick Tips
- Use `$A$1` to lock a cell reference (absolute)
- Use `Ctrl + Shift + L` to filter data
- Use `Alt + =` for quick sum