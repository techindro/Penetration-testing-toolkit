# 📈 Module 07: Power BI DAX Formulas & Shortcuts

Master list of essential DAX (Data Analysis Expressions) formulas, measures, time intelligence functions, and shortcuts for Power BI.

---

## ⚡ 1. Daily Keyboard Shortcuts

| Key Combination | Action |
| :--- | :--- |
| `Ctrl + Shift + L` | Toggle Field List pane. |
| `Shift + Enter` | Insert new line inside DAX formula bar. |
| `Ctrl + A` -> `Alt + Shift + F` | Auto-format DAX measure code. |

---

## 📐 2. Essential DAX Measures & Formulas

### A. Core Aggregation & CALCULATE Measures
```dax
-- Total Sales Measure
Total Sales = SUM(Sales[SalesAmount])

-- Filtered Sales for Specific Region using CALCULATE
Europe Sales = 
CALCULATE(
    SUM(Sales[SalesAmount]),
    Region[Continent] = "Europe"
)

-- Percentage of Total Sales
Sales Contribution % = 
DIVIDE(
    [Total Sales],
    CALCULATE([Total Sales], ALL(Sales)),
    0
)
```

### B. Time Intelligence DAX Functions
```dax
-- Year-to-Date (YTD) Sales
Sales YTD = TOTALYTD([Total Sales], 'Calendar'[Date])

-- Previous Year Sales (Same Period Last Year)
Sales SPLY = 
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR('Calendar'[Date])
)

-- Year-over-Year (YoY) Sales Growth %
Sales YoY Growth % = 
DIVIDE(
    [Total Sales] - [Sales SPLY],
    [Sales SPLY],
    0
)
```
