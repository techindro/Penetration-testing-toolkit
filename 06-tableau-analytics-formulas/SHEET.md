# 📊 Module 06: Tableau Analytics Formulas & Shortcuts

Essential calculated fields formulas, Level of Detail (LOD) expressions, string functions, and keyboard shortcuts for Tableau Desktop.

---

## ⚡ 1. Daily Keyboard Shortcuts

| Key Combination | Action |
| :--- | :--- |
| `Ctrl + W` | Swap Rows and Columns instantly on current sheet. |
| `Ctrl + M` | Open New Worksheet. |
| `Ctrl + Shift + M` | Open New Dashboard. |
| `F5` | Refresh Data Source connection. |
| `Ctrl + Drag Field` | Duplicate a field onto another shelf or card. |

---

## 📐 2. Essential Calculated Fields Formulas

### A. Conditional Logic (IF / CASE)
```sql
-- IF statement for Sales Performance Category
IF [Sales] > 50000 THEN "High Performer"
ELSEIF [Sales] >= 20000 THEN "Medium Performer"
ELSE "Low Performer"
END
```

### B. Level of Detail (LOD) Expressions

```sql
-- FIXED LOD: Calculate Total Sales per Region regardless of view filters
{ FIXED [Region] : SUM([Sales]) }

-- INCLUDE LOD: Calculate Average Sales per Customer including Sub-Category
{ INCLUDE [Customer Name] : AVG([Sales]) }

-- EXCLUDE LOD: Calculate Total Sales excluding Segment from view breakdown
{ EXCLUDE [Segment] : SUM([Sales]) }
```

### C. String & Date Calculations
```sql
-- Extract Year from Order Date
YEAR([Order Date])

-- Calculate Days Between Order Date and Ship Date
DATEDIFF('day', [Order Date], [Ship Date])

-- Upper case Customer Name
UPPER([Customer Name])
```
