# 📚 My Data Analytics Learning Log

---

## Week 1 - GitHub & Portfolio Setup (Aug 17-23, 2026)

### Day 1 (Aug 17)
- ✅ Created GitHub account
- ✅ Installed GitHub Desktop
- ✅ Created `data-analytics-portfolio` repo
- ✅ Wrote README with intro
- ✅ Learned: commit, push, pull
- ✅ Learned: .gitignore basics

### Day 2 (Aug 18)
- ✅ Created folder structure (projects, notes, datasets)
- ✅ Learned: Git tracks files, not folders
- 💡 Tip: Use placeholder files for empty folders

### Day 3 (Aug 19)
- ✅ Downloaded first dataset (retail sales)
- ✅ Learned: Text to Columns for date formatting
- ✅ Practiced: Basic Excel formulas (SUM, AVERAGE)

### Day 4 (Aug 20)
- ✅ Found and fixed inconsistent date formats
- ✅ Used Find & Replace to clean text in columns
- ✅ Documented cleaning steps in dataset-notes.md

### Day 5 (Aug 21)
- ✅ Learned about VLOOKUP and XLOOKUP
- ✅ Practiced merging two tables
- ✅ Created a simple lookup exercise file

### Day 6 (Aug 22)
- ✅ Explored Pivot Tables
- ✅ Summarized sales by region and product
- ✅ Created first pivot chart

### Day 7 (Aug 23)
- ✅ Applied fixes using Filter + Text to Columns
- ✅ Cleaned date column and other messy columns
- ✅ Completed first mini-project: Retail Sales Cleaning

---

## Week 2 - Kaggle Exploration & Advanced Cleaning (Aug 24-30)

### Day 8 (Aug 24)
- ✅ Downloaded new dataset: Personal Finance ML Dataset (32,424 rows, 20 columns)
- ✅ Explored structure and identified key columns: income, expenses, savings, DTI, region, education
- ✅ Set project goal: Build a Budget Tracker Dashboard

### Day 9 (Aug 25)
- ✅ Inspected date column (record_date) — consistent format found
- ✅ Verified categorical columns: education_level, employment_status, region
- ✅ Confirmed all columns are usable

### Day 10 (Aug 26)
- ✅ Discovered DTI column contained unrealistic values (up to 90)
- ✅ Researched: DTI > 2 is financially impossible
- ✅ Applied filter: removed rows with DTI > 2

### Day 11 (Aug 27)
- ✅ Discovered savings_to_income_ratio > 1 (savings exceeds income)
- ✅ Removed rows with savings_to_income_ratio > 1
- ✅ Dataset reduced from 32k to 2,495 realistic rows

### Day 12 (Aug 28)
- ✅ Final data quality check on all columns
- ✅ Verified: age, gender, education_level, employment_status, region are clean
- ✅ Verified: income, expenses, savings are realistic
- ✅ Documented all decisions in dataset-notes.md

### Day 13 (Aug 29)
- ✅ Created project folder: /projects/budget-tracker/
- ✅ Created cleaned data file: personal_finance_cleaned.xlsx
- ✅ Prepared for dashboard creation

### Day 14 (Aug 30)
- ✅ Final verification: dataset is analysis-ready
- ✅ Confirmed all cleaning steps documented
- ✅ Committed cleaned dataset to GitHub

---

## Week 3 - Budget Tracker Dashboard (Aug 31 - Sep 6)

### Day 15 (Aug 31)
- ✅ Created budget-dashboard.xlsx
- ✅ Copied cleaned data into dashboard file (Data sheet)
- ✅ Learned: Keeping data and dashboard separate is best practice

### Day 16 (Sep 1)
- ✅ Created dashboard layout: title, summary cards, chart sections
- ✅ Built summary cards: Total Records, Avg Income, Avg Expenses, Avg Savings, Avg DTI, High Risk Count
- ✅ Applied formulas to summary cards

### Day 17 (Sep 2)
- ✅ Created PivotTables sheet
- ✅ Built Pivot Table 1: Average Income by Region
- ✅ Built Pivot Table 2: Average Expenses by Region
- ✅ Built Pivot Table 3: Average Income by Education Level
- ✅ Built Pivot Table 4: High Risk Count by Region (DTI > 0.4)

### Day 18 (Sep 3)
- ✅ Created Charts sheet
- ✅ Created Pie Chart: Income vs Expenses vs Savings
- ✅ Created Bar Chart: Expenses by Region
- ✅ Created Bar Chart: Average DTI by Region
- ✅ Created Bar Chart: High Risk % by Region

### Day 19 (Sep 4)
- ✅ Added helper column: High_Risk (1 for DTI > 0.4, 0 for ≤ 0.4)
- ✅ Learned: Use SUM for count, AVERAGE for percentage in pivot tables
- ✅ Fixed High Risk % using Average trick in pivot table
- ✅ Finalized dashboard layout

### Day 20 (Sep 5)
- ✅ Added Slicers: Region, Education Level, Gender, Age
- ✅ Added Timeline: Record Date
- ✅ Connected all slicers and timeline to ALL pivot tables
- ✅ Tested interactivity — all charts update instantly

### Day 21 (Sep 6)
- ✅ Took screenshots of dashboard with different filters applied
- ✅ Recorded a 30-second video showing interactive features
- ✅ Polished dashboard design (colors, layout, formatting)
- ✅ Updated project README with dashboard preview and video link
- ✅ Committed and pushed final dashboard to GitHub

---

## 📊 Final Dashboard Features

- **Summary Cards:** Total Records, Income, Expenses, Savings, Avg DTI, High Risk Count
- **Interactive Slicers:** Age, Gender, Region, Education Level
- **Timeline:** Record Date range filter
- **Charts:** Pie chart + 3 bar charts (Expenses by Region, DTI by Region, High Risk by Region)
- **Cross-tab View:** High Risk by Region and Education

## 🏆 Skills Demonstrated

- Data cleaning (Excel)
- Outlier handling (DTI, savings rate)
- Pivot tables & calculated fields
- Slicers & timelines
- Dashboard design & layout
- Documentation & version control (Git/GitHub)

---

## 📁 Project Files

- `personal_finance_cleaned.xlsx` — Cleaned dataset (2,494 rows)
- `budget-dashboard.xlsx` — Interactive dashboard
- `dataset-notes.md` — Cleaning documentation
- `README.md` — Project summary with video demo

---

## 🌟 Key Takeaway

I took raw, messy data (32k+ rows), cleaned it to 2,494 realistic rows, and built a fully interactive dashboard with slicers and a timeline. The dashboard is now portfolio-ready and demonstrates real-world data analysis skills.

---

**Last Updated:** September 6, 2026