# SQLBolt - Lesson 8: A Short Note on NULLs

# 📘 Introduction

In SQL databases, sometimes data is missing.

Example:

| name | building |
|---|---|
| Yancy I. | NULL |

This means:

```text
No value assigned yet
```

In SQL, missing values are represented using:

# 🔥 NULL

---

# 🧠 What is NULL?

`NULL` means:

- missing value
- unknown value
- empty/undefined data

It is NOT:

- 0
- empty string ""
- false

NULL is a special SQL value.

---

# 🎯 Why NULL Values Matter

NULL values require special handling because:

- comparisons behave differently
- calculations can change
- joins can produce NULLs
- filtering requires special operators

---

# ⭐ Checking NULL Values

SQL uses:

| Operator | Meaning |
|---|---|
| IS NULL | value is NULL |
| IS NOT NULL | value exists |

---

# 🧠 Syntax

```sql
SELECT columns
FROM table
WHERE column IS NULL;
```

---

# 📂 Buildings Table

| building_name | capacity |
|---|---|
| 1e | 24 |
| 1w | 32 |
| 2e | 16 |
| 2w | 20 |

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
| Engineer | Yancy I. | NULL | 0 |
| Artist | Oliver P. | NULL | 0 |

---

# ✅ Exercise Solutions

---

# 1️⃣ Find the name and role of all employees who have not been assigned to a building

## Query

```sql
SELECT name, role
FROM employees
WHERE building IS NULL;
```

---

## 🧠 Explanation

We need employees whose building value is missing.

```sql
WHERE building IS NULL
```

checks for missing building assignments.

---

## ✅ Output

| name | role |
|---|---|
| Yancy I. | Engineer |
| Oliver P. | Artist |

---

# 2️⃣ Find the names of the buildings that hold no employees

## Query

```sql
SELECT b.building_name
FROM buildings b
LEFT JOIN employees e
ON b.building_name = e.building
WHERE e.building IS NULL;
```

---

## 🧠 Step-by-step Thinking

### Step 1 → Keep all buildings

```sql
FROM buildings b
LEFT JOIN employees e
```

LEFT JOIN keeps every building.

---

### Step 2 → Match employees

```sql
ON b.building_name = e.building
```

connects buildings with employees.

---

### Step 3 → Find buildings without employees

If no employee exists:

```text
e.building becomes NULL
```

So:

```sql
WHERE e.building IS NULL
```

returns empty buildings.

---

# 🎯 Important Understanding

## INNER JOIN

Keeps only matching rows.

---

## LEFT JOIN

Keeps all rows from left table.

Even unmatched rows survive.

---

# 🔥 NULL Rules (Very Important)

❌ Wrong:

```sql
WHERE building = NULL
```

---

✅ Correct:

```sql
WHERE building IS NULL
```

---

❌ Wrong:

```sql
WHERE building != NULL
```

---

✅ Correct:

```sql
WHERE building IS NOT NULL
```

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Find NULL values | `WHERE column IS NULL` |
| Find non-NULL values | `WHERE column IS NOT NULL` |
| Keep all left rows | `LEFT JOIN` |
| Find unmatched rows | `WHERE joined_column IS NULL` |

---

# 🚀 Practice Queries

```sql
SELECT *
FROM employees
WHERE building IS NULL;

SELECT *
FROM employees
WHERE building IS NOT NULL;

SELECT name, years_employed
FROM employees
WHERE years_employed IS NOT NULL;

SELECT b.building_name
FROM buildings b
LEFT JOIN employees e
ON b.building_name = e.building
WHERE e.building IS NULL;
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ What NULL means in SQL  
✅ Difference between NULL and empty values  
✅ How to check NULL values  
✅ Why IS NULL is used instead of = NULL  
✅ How LEFT JOIN creates NULL rows  
✅ How to find unmatched rows in joins

---

# 🏁 End of Lesson 8
