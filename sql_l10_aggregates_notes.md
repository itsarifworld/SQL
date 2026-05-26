# SQLBolt - Lesson 10: Queries with Aggregates (Pt. 1)

# 📘 Introduction

SQL aggregate functions help summarize data.

Instead of showing every row individually, aggregates calculate:

- totals
- averages
- maximum values
- minimum values
- counts

These functions are very important in real-world data analysis.

---

# 🧠 What are Aggregate Functions?

Aggregate functions operate on multiple rows and return a single summarized value.

Example questions:

- How many employees exist?
- What is the average salary?
- What is the maximum experience?

---

# ⭐ Aggregate Function Syntax

```sql
SELECT AGG_FUNC(column)
FROM table_name;
```

---

# 🔥 Common Aggregate Functions

| Function | Meaning |
|---|---|
| COUNT() | count rows |
| MIN() | smallest value |
| MAX() | largest value |
| AVG() | average value |
| SUM() | total sum |

---

# 🧠 COUNT()

Counts rows.

## Example

```sql
SELECT COUNT(*)
FROM employees;
```

---

# 🧠 MIN()

Finds smallest value.

## Example

```sql
SELECT MIN(years_employed)
FROM employees;
```

---

# 🧠 MAX()

Finds largest value.

## Example

```sql
SELECT MAX(years_employed)
FROM employees;
```

---

# 🧠 AVG()

Finds average value.

## Example

```sql
SELECT AVG(years_employed)
FROM employees;
```

---

# 🧠 SUM()

Finds total value.

## Example

```sql
SELECT SUM(years_employed)
FROM employees;
```

---

# ⭐ GROUP BY

`GROUP BY` divides rows into groups.

Then aggregate functions run separately on each group.

---

# 🧠 GROUP BY Syntax

```sql
SELECT column, AGG_FUNC(column)
FROM table
GROUP BY column;
```

---

# 📂 Employees Table

| role | name | building | years_employed |
|---|---|---|---|
| Engineer | Becky A. | 1e | 4 |
| Engineer | Dan B. | 1e | 2 |
| Engineer | Sharon F. | 1e | 6 |
| Engineer | Dan M. | 1e | 4 |
| Engineer | Malcom S. | 1e | 1 |
| Artist | Tylar S. | 2w | 2 |
| Artist | Sherman D. | 2w | 8 |
| Artist | Jakob J. | 2w | 6 |
| Artist | Lillia A. | 2w | 7 |
| Artist | Brandon J. | 2w | 7 |
| Manager | Scott K. | 1e | 9 |
| Manager | Shirlee M. | 1e | 3 |
| Manager | Daria O. | 2w | 6 |

---

# ✅ Exercise Solutions

---

# 1️⃣ Find the longest time that an employee has been at the studio

## Query

```sql
SELECT MAX(years_employed) AS longest_time
FROM employees;
```

---

## 🧠 Explanation

```sql
MAX(years_employed)
```

finds highest value in years_employed column.

---

## ✅ Output

```text
9
```

because Scott K. worked 9 years.

---

# 2️⃣ For each role, find the average number of years employed

## Query

```sql
SELECT role,
       AVG(years_employed) AS average_years
FROM employees
GROUP BY role;
```

---

## 🧠 Explanation

### GROUP BY role

Creates groups:

- Engineers
- Artists
- Managers

---

### AVG(years_employed)

Calculates average separately for each group.

---

## ✅ Example Output

| role | average_years |
|---|---|
| Engineer | 3.4 |
| Artist | 6 |
| Manager | 6 |

---

# 3️⃣ Find the total number of employee years worked in each building

## Query

```sql
SELECT building,
       SUM(years_employed) AS total_years
FROM employees
GROUP BY building;
```

---

## 🧠 Explanation

### GROUP BY building

Creates groups for each building.

---

### SUM(years_employed)

Adds all employee years inside each building.

---

## ✅ Example Output

| building | total_years |
|---|---|
| 1e | 29 |
| 2w | 36 |

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| Aggregate Function | summarize rows |
| MAX() | highest value |
| MIN() | smallest value |
| AVG() | average |
| SUM() | total |
| COUNT() | count rows |
| GROUP BY | divide rows into groups |

---

# 🔥 Most Important Understanding

Without GROUP BY:

```sql
SELECT AVG(years_employed)
FROM employees;
```

returns ONE average for entire table.

---

With GROUP BY:

```sql
SELECT role, AVG(years_employed)
FROM employees
GROUP BY role;
```

returns separate averages for each role.

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Find maximum | `MAX(column)` |
| Find minimum | `MIN(column)` |
| Find average | `AVG(column)` |
| Find total | `SUM(column)` |
| Count rows | `COUNT(*)` |
| Create groups | `GROUP BY column` |

---

# 🚀 Practice Queries

```sql
SELECT COUNT(*)
FROM employees;

SELECT MIN(years_employed)
FROM employees;

SELECT role,
       COUNT(*)
FROM employees
GROUP BY role;

SELECT building,
       AVG(years_employed)
FROM employees
GROUP BY building;

SELECT role,
       SUM(years_employed)
FROM employees
GROUP BY role;
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ What aggregate functions are  
✅ How MAX(), MIN(), AVG(), SUM(), COUNT() work  
✅ How GROUP BY creates groups  
✅ Difference between grouped and non-grouped aggregates  
✅ How SQL summarizes large datasets

---

# 🏁 End of Lesson 10
