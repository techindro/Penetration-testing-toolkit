# 📗 Module 08: MS Excel Master Formulas & Examples

Comprehensive reference for modern Excel formulas (`XLOOKUP`, `INDEX+MATCH`, `SUMIFS`, `IFS`), keyboard shortcuts, and data analysis tricks with concrete examples.

---

## ⚡ 1. Daily Keyboard Shortcuts & Examples

| Key Combination | Action | Practical Usage Example |
| :--- | :--- | :--- |
| `F4` | Toggle cell reference modes. | Type `=A1*B1`, highlight `A1` and press `F4` to turn it into absolute `$A$1` (locks cell while dragging formula down). |
| `Alt + =` | Instant AutoSum. | Select cell below a column of numbers, press `Alt+=` to instantly generate `=SUM(A1:A20)`. |
| `Ctrl + Shift + L` | Toggle AutoFilter. | Press `Ctrl+Shift+L` on a data header to instantly add dropdown filter arrows. |
| `Ctrl + T` | Create Official Table. | Select data range, press `Ctrl+T` to convert plain rows into formatted Excel Table with zebra stripes. |
| `Ctrl + 1` | Format Cells window. | Select number cell, press `Ctrl+1` to format as Currency, Date, or Percentage. |

---

## 📐 2. Essential Excel Master Formulas with Examples

### A. XLOOKUP (Modern Replacement for VLOOKUP)
```excel
Syntax: =XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found])

-- Practical Example: Look up Employee Name in Col B using Employee ID typed in cell E2
=XLOOKUP(E2, A2:A100, B2:B100, "Employee Not Found")

-- Sample Data:
-- Col A (Emp ID): 101, 102, 103
-- Col B (Emp Name): Rahul, Priya, Amit
-- Formula Result for E2=102: "Priya"
```

### B. INDEX + MATCH (Flexible Left/Right Lookup)
```excel
Syntax: =INDEX(return_range, MATCH(lookup_value, lookup_range, 0))

-- Practical Example: Find Product Price in Col A by searching Product Name in Col C (Left Lookup!)
=INDEX(A2:A100, MATCH("Laptop", C2:C100, 0))

-- Sample Data:
-- Col A (Price): $500, $1200
-- Col C (Product Name): Mouse, Laptop
-- Formula Result: $1200
```

### C. SUMIFS & COUNTIFS (Multi-Condition Aggregations)
```excel
-- Practical Example 1: SUMIFS
-- Sum Total Revenue (Col C) where Region is "West" (Col A) AND Year is 2026 (Col B)
=SUMIFS(C2:C100, A2:A100, "West", B2:B100, 2026)
-- Output: Returns total revenue sum for 2026 West orders.

-- Practical Example 2: COUNTIFS
-- Count total completed orders with value greater than $1000
=COUNTIFS(A2:A100, "Completed", B2:B100, ">1000")
-- Output: 14 (Total matching completed orders).
```

### D. IFS & TEXTJOIN Examples
```excel
-- Practical Example 1: IFS
-- Grade evaluation without nested IFs
=IFS(A2>=90, "Grade A", A2>=80, "Grade B", A2>=70, "Grade C", TRUE, "Grade F")
-- Result for A2=85: "Grade B"

-- Practical Example 2: TEXTJOIN
-- Combine names in cells A2 to A4 separated by comma, skipping blank cells
=TEXTJOIN(", ", TRUE, A2:A4)
-- Sample Data: A2="Apple", A3="", A4="Banana" -> Result: "Apple, Banana"
```
