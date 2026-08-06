# 🗄️ Module 29: SQL Interview Queries, Window Functions & CTEs

Essential SQL query patterns, Window Functions (`ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`), Common Table Expressions (CTEs), and Joins asked in database interviews.

---

## 📊 1. Window Functions (`ROW_NUMBER` vs `RANK` vs `DENSE_RANK`)

```sql
-- Example: Ranking employees by salary within each department
SELECT 
    employee_id,
    department_id,
    salary,
    ROW_NUMBER() OVER (PARTITION BY department_id ORDER BY salary DESC) as row_num,
    RANK()       OVER (PARTITION BY department_id ORDER BY salary DESC) as rank_val,
    DENSE_RANK() OVER (PARTITION BY department_id ORDER BY salary DESC) as dense_rank_val
FROM employees;
```
* **`ROW_NUMBER()`**: Always unique sequential integers (1, 2, 3, 4).
* **`RANK()`**: Skips rank values after ties (1, 2, 2, 4).
* **`DENSE_RANK()`**: Does NOT skip rank values after ties (1, 2, 2, 3).

---

## 🏆 2. Finding Nth Highest Salary (Classic Interview Query)

```sql
-- Query: Find 2nd Highest Salary using DENSE_RANK()
WITH RankedSalaries AS (
    SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) as rnk
    FROM employees
)
SELECT DISTINCT salary 
FROM RankedSalaries 
WHERE rnk = 2;
```

---

## 🔍 3. Group By with HAVING Clause

```sql
-- Query: Find departments with more than 5 active employees and average salary > 70000
SELECT department_id, COUNT(*) as emp_count, AVG(salary) as avg_sal
FROM employees
WHERE status = 'active'
GROUP BY department_id
HAVING COUNT(*) > 5 AND AVG(salary) > 70000;
```
