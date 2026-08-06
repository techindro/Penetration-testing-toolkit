# 📗 Module 08: MS Excel Master Formulas & Shortcuts

Comprehensive reference for modern Excel formulas (`XLOOKUP`, `INDEX+MATCH`, `SUMIFS`, `IFS`), keyboard shortcuts, and data analysis tricks.

---

## ⚡ 1. Daily Keyboard Shortcuts

| Key Combination | Action (Simple Explanation) |
| :--- | :--- |
| `F4` | Toggle cell reference modes (Absolute `$A$1`, Relative `A1`, Row `$A1`, Column `A$1`). |
| `Alt + =` | Instant AutoSum (Sums selected row or column numbers immediately). |
| `Ctrl + Shift + L` | Toggle AutoFilter on/off for current table. |
| `Ctrl + T` | Convert selected range into an Official Excel Table. |
| `Ctrl + 1` | Open Format Cells dialog window. |
| `Ctrl + Arrow Key` | Jump to the very edge of data in that direction. |
| `Ctrl + Shift + Arrow Key` | Select all cells to the edge of data in that direction. |

---

## 📐 2. Essential Excel Master Formulas

### A. XLOOKUP (Modern Replacement for VLOOKUP)
```excel
=XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found])

-- Example: Find Employee Name (Col B) by searching Employee ID (Col A)
=XLOOKUP(E2, A2:A100, B2:B100, "Employee Not Found")
```

### B. INDEX + MATCH (Flexible Left/Right Lookup)
```excel
=INDEX(return_range, MATCH(lookup_value, lookup_range, 0))

-- Example: Find Price in Col A based on Product Name in Col C
=INDEX(A2:A100, MATCH("Laptop", C2:C100, 0))
```

### C. SUMIFS & COUNTIFS (Multi-Condition Aggregations)
```excel
-- SUMIFS: Sum Total Sales (Col C) where Region is "West" (Col A) and Year is 2026 (Col B)
=SUMIFS(C2:C100, A2:A100, "West", B2:B100, 2026)

-- COUNTIFS: Count orders where Status is "Completed" (Col A) and Value > 1000 (Col B)
=COUNTIFS(A2:A100, "Completed", B2:B100, ">1000")
```

### D. IFS & TEXTJOIN
```excel
-- IFS: Multiple conditions without nested IF statements
=IFS(A2>=90, "Grade A", A2>=80, "Grade B", A2>=70, "Grade C", TRUE, "Grade F")

-- TEXTJOIN: Join text strings with delimiter, ignoring empty cells
=TEXTJOIN(", ", TRUE, A2:A10)
```
