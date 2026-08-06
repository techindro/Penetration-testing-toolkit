# 📈 Module 07: Power BI DAX Formulas & Examples

Master list of DAX (Data Analysis Expressions) formulas, measures, time intelligence functions, and shortcuts with concrete practical examples.

---

## ⚡ 1. Daily Keyboard Shortcuts & Examples

| Key Combination | Action | Practical Example |
| :--- | :--- | :--- |
| `Ctrl + Shift + L` | Toggle Field List. | Press `Ctrl+Shift+L` to hide fields pane and expand report visual canvas. |
| `Shift + Enter` | New line in DAX formula. | Press `Shift+Enter` to write multiline readable DAX measures cleanly. |
| `Ctrl + A` -> `Alt + Shift + F` | Format DAX code. | Press `Alt+Shift+F` inside DAX editor to auto-indent complex DAX expressions. |

---

## 📐 2. Essential DAX Measures & Examples

### A. Core Aggregation & CALCULATE Examples
```dax
-- Example 1: Total Sales Measure
Total Sales = SUM(Sales[SalesAmount])
-- Result: Sums up all values in SalesAmount column.

-- Example 2: Filtered Sales for Specific Region using CALCULATE
Europe Sales = 
CALCULATE(
    SUM(Sales[SalesAmount]),
    Region[Continent] = "Europe"
)
-- Result: Computes total sales specifically for Europe region regardless of slicer selections.

-- Example 3: Percentage of Total Sales
Sales Contribution % = 
DIVIDE(
    [Total Sales],
    CALCULATE([Total Sales], ALL(Sales)),
    0
)
-- Result: If Product A sales = $200 and Total Sales = $1000, returns 0.20 (20%).
```

### B. Time Intelligence DAX Examples
```dax
-- Example 1: Year-to-Date (YTD) Sales
Sales YTD = TOTALYTD([Total Sales], 'Calendar'[Date])
-- Result: Accumulates Total Sales from Jan 1st up to current selected date.

-- Example 2: Previous Year Sales (Same Period Last Year)
Sales SPLY = 
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR('Calendar'[Date])
)
-- Result: If current selection is Aug 2026 ($50,000), returns Aug 2025 sales ($42,000).

-- Example 3: Year-over-Year (YoY) Sales Growth %
Sales YoY Growth % = 
DIVIDE(
    [Total Sales] - [Sales SPLY],
    [Sales SPLY],
    0
)
-- Result: Computes YoY percentage growth: ($50,000 - $42,000) / $42,000 = +19.04%.
```
