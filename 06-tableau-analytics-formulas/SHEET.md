# 📊 Module 06: Tableau Analytics Formulas & Examples

Essential calculated fields formulas, Level of Detail (LOD) expressions, string functions, and keyboard shortcuts with clear practical examples.

---

## ⚡ 1. Daily Keyboard Shortcuts & Examples

| Key Combination | Action | Practical Example |
| :--- | :--- | :--- |
| `Ctrl + W` | Swap Rows and Columns. | Press `Ctrl+W` to flip a horizontal bar chart into a vertical bar chart instantly. |
| `Ctrl + M` | Open New Worksheet. | Press `Ctrl+M` to add a new sheet without clicking the bottom tab bar. |
| `Ctrl + Shift + M` | Open New Dashboard. | Press `Ctrl+Shift+M` to create a blank dashboard canvas. |
| `F5` | Refresh Data Source. | Press `F5` after adding new rows in your Excel / SQL database to update Tableau data. |
| `Ctrl + Drag Field` | Duplicate field on shelf. | Hold `Ctrl` while dragging `SUM(Sales)` from Color card to Size card to duplicate it. |

---

## 📐 2. Essential Calculated Fields Formulas with Examples

### A. Conditional Logic (IF / CASE) Example
```sql
-- Calculated Field Name: Performance Category
IF [Sales] > 50000 THEN "High Performer"
ELSEIF [Sales] >= 20000 THEN "Medium Performer"
ELSE "Low Performer"
END

-- Practical Result Example:
-- Order 101 ($65,000) -> "High Performer"
-- Order 102 ($15,000) -> "Low Performer"
```

### B. Level of Detail (LOD) Expressions Examples

```sql
-- Example 1: FIXED LOD - Calculate Total Regional Sales regardless of category filter
{ FIXED [Region] : SUM([Sales]) }
-- Result: Displays $1,200,000 for "West Region" even if user filters for "Technology" subcategory only.

-- Example 2: INCLUDE LOD - Calculate Average Customer Sales per Sub-Category
{ INCLUDE [Customer Name] : AVG([Sales]) }
-- Result: Computes granular customer purchase average included in high-level subcategory view.

-- Example 3: EXCLUDE LOD - Calculate Total Sales excluding Segment from view breakdown
{ EXCLUDE [Segment] : SUM([Sales]) }
-- Result: Ignores Segment breakdown to compute overall total sales for ratio calculations.
```

### C. Date Calculation Example
```sql
-- Calculated Field Name: Delivery Days
DATEDIFF('day', [Order Date], [Ship Date])

-- Practical Result Example:
-- Order Date: 2026-08-01, Ship Date: 2026-08-05 -> Output: 4 days
```
