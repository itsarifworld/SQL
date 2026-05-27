# SQLBolt - Lesson 15: Deleting Rows

# 📘 Introduction

Sometimes data is no longer needed.

Examples:

- removing old records
- deleting wrong entries
- cleaning databases

SQL uses:

# 🔥 DELETE

to remove rows from a table.

---

# 🧠 DELETE Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

---

# 🧠 Important Parts

| Part | Meaning |
|---|---|
| DELETE FROM | choose table |
| WHERE | choose rows to delete |

---

# ⚠️ VERY IMPORTANT WARNING

If you forget:

```sql
WHERE condition
```

then SQL deletes:

# ❌ ALL ROWS

---

# Dangerous Example

```sql
DELETE FROM movies;
```

This removes every movie.

---

# 🔥 Best Practice

Always test condition first using SELECT.

---

# Example

## First test

```sql
SELECT *
FROM movies
WHERE year < 2005;
```

---

## Then delete

```sql
DELETE FROM movies
WHERE year < 2005;
```

---

# 📂 Movies Table

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 4 | Monsters, Inc. | Pete Docter | 2001 | 92 |
| 5 | Finding Nemo | Andrew Stanton | 2003 | 107 |
| 6 | The Incredibles | Brad Bird | 2004 | 116 |
| 7 | Cars | John Lasseter | 2006 | 117 |

---

# ✅ Exercise Solutions

---

# 1️⃣ Remove all movies released before 2005

## Query

```sql
DELETE FROM movies
WHERE year < 2005;
```

---

## 🧠 Explanation

### WHERE year < 2005

selects movies older than 2005.

---

### DELETE FROM movies

removes those rows.

---

# 2️⃣ Remove all movies directed by Andrew Stanton

## Query

```sql
DELETE FROM movies
WHERE director = 'Andrew Stanton';
```

---

## 🧠 Explanation

### WHERE director = 'Andrew Stanton'

finds Andrew Stanton movies.

---

### DELETE

removes matching rows.

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| DELETE | remove rows |
| WHERE | choose rows |
| Missing WHERE | deletes all rows |

---

# 🔥 Most Important Understanding

## Safe Delete Workflow

### Step 1

Test rows first:

```sql
SELECT *
FROM movies
WHERE director = 'Andrew Stanton';
```

---

### Step 2

Run DELETE query.

---

# ⚠️ Common Mistake

❌ Dangerous:

```sql
DELETE FROM movies;
```

Deletes ALL movies.

---

# ✅ Safe:

```sql
DELETE FROM movies
WHERE id = 5;
```

Deletes only one row.

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Delete rows | `DELETE FROM table` |
| Delete specific rows | `WHERE condition` |
| Delete all rows | no WHERE clause |

---

# 🚀 Practice Queries

```sql
DELETE FROM movies
WHERE year > 2010;

DELETE FROM movies
WHERE title = 'Cars';

DELETE FROM movies
WHERE director = 'Brad Bird';

SELECT *
FROM movies
WHERE year < 2000;
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ How DELETE works  
✅ How to remove rows safely  
✅ Why WHERE is critical in DELETE  
✅ How to test rows before deleting  
✅ Difference between deleting some rows and all rows

---

# 🏁 End of Lesson 15
