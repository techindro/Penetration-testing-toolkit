# 📗 Module 08: MS Excel Master Formulas (Easy to Hard)

Excel formulas and shortcuts categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Formulas & Shortcuts

```excel
-- 1. AutoSum Shortcut (Press Alt + =)
-- Sums column values instantly
=SUM(A1:A20)

-- 2. Average Formula
=AVERAGE(B2:B50)

-- 3. Basic IF Statement
=IF(A2>=50, "Pass", "Fail")
```

---

## 🟡 Level 2: Medium / Intermediate Formulas

```excel
-- 1. XLOOKUP (Modern replacement for VLOOKUP)
=XLOOKUP(E2, A2:A100, B2:B100, "Not Found")

-- 2. SUMIFS (Multi-condition sum)
=SUMIFS(C2:C100, A2:A100, "West", B2:B100, 2026)

-- 3. IFS (Multiple conditions without nested IFs)
=IFS(A2>=90, "Grade A", A2>=80, "Grade B", TRUE, "Grade C")
```

---

## 🔴 Level 3: Hard / Advanced Master Formulas

```excel
-- 1. INDEX + MATCH (Flexible Left/Right Lookup)
=INDEX(A2:A100, MATCH("Laptop", C2:C100, 0))

-- 2. TEXTJOIN with Conditional Arrays
=TEXTJOIN(", ", TRUE, A2:A20)

-- 3. Dynamic Cell Reference Lock (F4 key)
-- $A$1 (Locked Row & Column during copy down)
```
