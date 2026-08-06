# 📗 Module 08: MS Excel Master Formulas & Shortcuts (30+ Sheet)

Complete reference for 30+ Excel formulas, lookup functions, data manipulations, and keyboard shortcuts categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Formulas & Shortcuts (1 - 10)

```excel
-- 1. AutoSum Shortcut (Press Alt + =)
-- Sums selected column or row values instantly
=SUM(A1:A20)

-- 2. Average Formula
=AVERAGE(B2:B50)

-- 3. Minimum Value
=MIN(C2:C100)

-- 4. Maximum Value
=MAX(C2:C100)

-- 5. Count Numbers in Range
=COUNT(A2:A100)

-- 6. Count Non-Blank Cells
=COUNTA(A2:A100)

-- 7. Basic IF Condition Statement
=IF(A2>=50, "Pass", "Fail")

-- 8. Convert Text to Upper Case
=UPPER(A2)

-- 9. Convert Text to Lower Case
=LOWER(A2)

-- 10. Trim Extra Spaces from Text
=TRIM(A2)
```

---

## 🟡 Level 2: Medium / Intermediate Formulas (11 - 20)

```excel
-- 11. XLOOKUP (Modern VLOOKUP Replacement - Exact Match)
=XLOOKUP(E2, A2:A100, B2:B100, "Not Found")

-- 12. SUMIFS (Multi-condition Sum)
=SUMIFS(C2:C100, A2:A100, "West", B2:B100, 2026)

-- 13. COUNTIFS (Multi-condition Count)
=COUNTIFS(A2:A100, "West", B2:B100, ">50")

-- 14. AVERAGEIFS (Multi-condition Average)
=AVERAGEIFS(C2:C100, A2:A100, "East", B2:B100, 2026)

-- 15. IFS (Multiple conditions without nested IF statements)
=IFS(A2>=90, "Grade A", A2>=80, "Grade B", A2>=70, "Grade C", TRUE, "Fail")

-- 16. IFERROR (Replace calculation errors with custom text)
=IFERROR(A2/B2, 0)

-- 17. CONCATENATE / TEXTJOIN (Join text with delimiter)
=TEXTJOIN(", ", TRUE, A2:A10)

-- 18. Extract Left Characters from Text
=LEFT(A2, 5)

-- 19. Extract Right Characters from Text
=RIGHT(A2, 4)

-- 20. Calculate Difference in Days Between Dates
=DATEDIF(A2, B2, "d")
```

---

## 🔴 Level 3: Hard / Advanced Master Formulas & Keyboard Tricks (21 - 30)

```excel
-- 21. INDEX + MATCH (Flexible Left & Right Lookup)
=INDEX(A2:A100, MATCH("Laptop", C2:C100, 0))

-- 22. Dynamic Array FILTER Function
=FILTER(A2:C100, C2:C100="Completed", "No Results")

-- 23. SORT Function (Sort Range Dynamically)
=SORT(A2:C100, 2, -1)  -- Sorts by 2nd column descending

-- 24. UNIQUE Function (Extract Unique Items List)
=UNIQUE(A2:A100)

-- 25. Absolute Cell Reference Lock (F4 Key)
-- $A$1 (Locks both row and column during formula copy down)

-- 26. Fill Down Shortcut (Copy formula from cell above)
Ctrl + D

-- 27. Fill Right Shortcut (Copy formula from left cell)
Ctrl + R

-- 28. Open Format Cells Dialog Window
Ctrl + 1

-- 29. Insert Current System Date
Ctrl + ;

-- 30. Toggle Formula View Mode (Show all cell formulas)
Ctrl + `
```
