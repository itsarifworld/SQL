# SQLBolt - Lesson 14: Updating Rows

# 📘 Introduction

SQL databases not only store data, they also allow us to modify existing data.

To change existing rows, SQL uses:

# 🔥 UPDATE

---

# 🧠 What is UPDATE?

`UPDATE` changes existing values inside a table.

Example:

- fixing incorrect names
- correcting dates
- changing salaries
- updating emails

---

# ⭐ UPDATE Syntax

```sql
UPDATE table_name
SET column = new_value
WHERE condition;
```

---

# 🧠 Important Parts

| Part | Meaning |
|---|---|
| UPDATE | choose table |
| SET | specify new values |
| WHERE | choose rows to update |

---

# ⭐ Updating Multiple Columns

You can update multiple columns together.

## Example

```sql
UPDATE movies
SET title = 'Toy Story 3',
    director = 'Lee Unkrich'
WHERE id = 11;
```

---

# ⚠️ VERY IMPORTANT WARNING

If you forget:

```sql
WHERE condition
```

then SQL updates:

# ❌ ALL ROWS

---

# Example of Dangerous Query

```sql
UPDATE movies
SET director = 'John Lasseter';
```

This changes every movie director.

---

# 🔥 Best Practice

Always test condition first using SELECT.

---

# Example

## First test

```sql
SELECT *
FROM movies
WHERE id = 2;
```

---

## Then update

```sql
UPDATE movies
SET director = 'John Lasseter'
WHERE id = 2;
```

---

# 📂 Movies Table

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | El Directore | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1899 | 93 |
| 11 | Toy Story 8 | El Directore | 2010 | 103 |

---

# ✅ Exercise Solutions

---

# 1️⃣ Fix the director of A Bug's Life

## Query

```sql
UPDATE movies
SET director = 'John Lasseter'
WHERE title = "A Bug's Life";
```

---

## 🧠 Explanation

### WHERE title = "A Bug's Life"

finds correct movie row.

---

### SET director

changes director value.

---

# 2️⃣ Fix release year of Toy Story 2

## Query

```sql
UPDATE movies
SET year = 1999
WHERE title = 'Toy Story 2';
```

---

## 🧠 Explanation

### SET year = 1999

updates incorrect year.

---

# 3️⃣ Fix Toy Story 8 title and director

## Query

```sql
UPDATE movies
SET title = 'Toy Story 3',
    director = 'Lee Unkrich'
WHERE id = 11;
```

---

## 🧠 Explanation

### Multiple column update

```sql
SET title = ...,
    director = ...
```

updates both columns together.

---

### WHERE id = 11

ensures only one row changes.

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| UPDATE | modify rows |
| SET | new values |
| WHERE | select rows |
| Multiple SET | update multiple columns |

---

# 🔥 Most Important Understanding

## Safe Update Workflow

### Step 1

Test row selection:

```sql
SELECT *
FROM movies
WHERE id = 11;
```

---

### Step 2

Run UPDATE query.

---

# ⚠️ Common Mistake

❌ Missing WHERE clause

```sql
UPDATE movies
SET year = 2025;
```

This updates ALL rows.

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Update one column | `SET col = value` |
| Update multiple columns | `SET col1 = v1, col2 = v2` |
| Update specific rows | `WHERE condition` |

---

# 🚀 Practice Queries

```sql
UPDATE movies
SET director = 'Brad Bird'
WHERE title = 'Cars';

UPDATE movies
SET year = 2010
WHERE id = 3;

UPDATE movies
SET title = 'Finding Dory',
    year = 2016
WHERE id = 5;

SELECT *
FROM movies
WHERE director = 'John Lasseter';
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ How UPDATE works  
✅ How to modify existing rows  
✅ How SET changes values  
✅ Why WHERE is important in updates  
✅ How to update multiple columns safely

---

# 🏁 End of Lesson 14
