# 📚 My Data Analytics Learning Log (Excel Focus)

## Week 1 - GitHub & Portfolio Setup (Aug 17-23, 2026)

### Day 1 (Aug 17)
- ✅ Created GitHub account
- ✅ Installed GitHub Desktop
- ✅ Created `data-analytics-portfolio` repo
- ✅ Wrote README with intro
- ✅ Learned: commit, push, pull
- ✅ Learned: .gitignore basics

### Day 2 (Aug 18)
- ✅ Created folder structure
- ✅ Learned: Git tracks files, not folders
- 📂 Added placeholder files

### Day 3 (Aug 19)
- ✅ Added this learning log
- 📊 Decided to focus on Excel first

### Day 3 (Aug 20)
- ✅ Create account on Kaggle
- ✅ Downloaded datasets from Kaggle

### Day 4 (Aug 20)
- ✅ Attend training on data Cleaning
- ✅ Attempted to commence data cleaning

### Day 5 (Aug 21)
- ✅ Commenced data cleaning, run into inconsistent date issue

### Day 6 (Aug 22)
- ✅ Solved the challenges

### Day 7 (Aug 23)
- ✅ Apply the fix (Filter, Data - Text to Column ...)
- ✅ Cleaned the date column and other messy columns
- ✅ Project completed

### Week 2 (Aug 24 - Aug 30) - Data Cleaning & Kaggle Exploration

#### Day 8 (Aug 24)
- ✅ Downloaded new dataset from Kaggle: Personal Finance ML Dataset
- ✅ Explored dataset structure: 32,424 rows, 20 columns
- ✅ Identified target columns for budget tracker: income, expenses, savings, DTI

#### Day 9 (Aug 25)
- ✅ Inspected date column for consistency (record_date)
- ✅ Checked categorical columns: education_level, employment_status, region
- ✅ Verified data types and formatting

#### Day 10 (Aug 26)
- ✅ Found and fixed inconsistent date formats
- ✅ Used Text to Columns to standardize dates
- ✅ Documented cleaning steps in dataset-notes.md

#### Day 11 (Aug 27)
- ✅ Discovered DTI column contains unrealistic values (up to 90)
- ✅ Researched: DTI > 2 is financially impossible
- ✅ Applied filter: removed rows with DTI > 2
- ✅ Result: Cleaned DTI range now 0 to 2

#### Day 12 (Aug 28)
- ✅ Discovered savings_to_income_ratio > 1 (savings exceeds income)
- ✅ Removed rows with savings_to_income_ratio > 1
- ✅ Learned: This ensures realistic financial profiles
- ✅ Dataset reduced from 32k to 2,495 rows (quality over quantity)

#### Day 13 (Aug 29)
- ✅ Final data quality check on all columns
- ✅ Verified: age, gender, education_level, employment_status, region are clean
- ✅ Verified: income, expenses, savings are realistic
- ✅ Documented all decisions in dataset-notes.md

#### Day 14 (Aug 30)
- ✅ Confirmed data is analysis-ready
- ✅ Created project folder: /projects/budget-tracker/
- ✅ Created file: personal_finance_cleaned.xlsx
- ✅ Prepared for dashboard creation

---

### Week 3 (Aug 31 - Sep 6) - Budget Tracker Dashboard

#### Day 15 (Aug 31)
- ✅ Created budget-dashboard.xlsx
- ✅ Copied cleaned data into dashboard file (Data sheet)
- ✅ Learned: Keeping data and dashboard separate is best practice

#### Day 16 (Sep 1)
- ✅ Created dashboard layout: title, summary cards, chart sections
- ✅ Built summary cards: Total Records, Avg Income, Avg Expenses, Avg Savings, Avg DTI, High Risk %, Avg Savings Rate
- ✅ Applied formulas to summary cards

#### Day 17 (Sep 2)
- ✅ Created PivotTables sheet
- ✅ Built Pivot Table 1: Average Income by Region
- ✅ Built Pivot Table 2: Average Expenses by Region
- ✅ Built Pivot Table 3: Average Income by Education Level
- ✅ Built Pivot Table 4: High Risk Count by Region (DTI > 0.4)

#### Day 18 (Sep 3)
- ✅ Created Charts sheet
- ✅ Created Pie Chart: Income vs Expenses vs Savings
- ✅ Created Bar Chart: Expenses by Region
- ✅ Created Bar Chart: Average DTI by Region
- ✅ Created Bar Chart: High Risk % by Region
- ✅ Learned: Copy charts to Dashboard sheet for final layout

#### Day 19 (Sep 4)
- ✅ Finalized dashboard layout
- ✅ Applied conditional formatting: DTI > 0.4 highlighted red
- ✅ Verified all formulas and pivot tables are working
- ✅ Dashboard complete and analysis-ready

#### Day 20 (Sep 5)
- ✅ Updated dataset-notes.md with final cleaning summary
- ✅ Updated project README.md with dashboard preview
- ✅ Documented key insights from dashboard
- ✅ Project ready for GitHub

---

## 📊 Key Insights from Budget Tracker
- **Total Records:** 2,495 (after cleaning)
- **Average Income:** $5,200
- **Average Expenses:** $3,800
- **Average Savings:** $1,400
- **Average DTI:** 0.35
- **High Risk Population (DTI > 0.4):** 15%
- **Top Spending Region:** [Your finding]
- **Highest Income by Education:** [Your finding]
---

## Excel Topics to Cover
- [ ] Basic formulas (SUM, AVERAGE, COUNT, etc)
- [ ] VLOOKUP / XLOOKUP
- [ ] Pivot Tables
- [ ] Data Cleaning (Text to Columns, Remove Duplicates)
- [ ] Conditional Formatting
- [ ] Charts & Visualization
- [ ] Dashboards

---

## Resources
- [Excel Tutorial Playlist]

- [Practice Datasets]