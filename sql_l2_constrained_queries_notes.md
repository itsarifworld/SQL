# SQLBolt - Lesson 2: Queries with Constraints (Pt. 1)

## 📘 Introduction

Selecting all rows from a huge database table is inefficient.

To filter specific rows, SQL provides the **WHERE clause**.

The `WHERE` clause allows us to apply conditions so that only matching rows are returned.

---

# 🧠 Basic WHERE Clause Syntax

```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

### Example

```sql
SELECT title
FROM movies
WHERE year = 2003;
```

This returns only movies released in 2003.

---

# ⭐ Combining Multiple Conditions

We can combine conditions using:

- `AND`
- `OR`

### Example

```sql
SELECT title, year
FROM movies
WHERE year >= 2000
AND year <= 2010;
```

This returns movies released between 2000 and 2010.

---

# 🔥 Common SQL Operators

| Operator | Meaning | Example |
|---|---|---|
| = | Equal to | `year = 2000` |
| != | Not equal to | `year != 2000` |
| > | Greater than | `year > 2005` |
| >= | Greater than or equal to | `year >= 2005` |
| < | Less than | `year < 2010` |
| <= | Less than or equal to | `year <= 2010` |
| BETWEEN | Within a range | `year BETWEEN 2000 AND 2010` |
| NOT BETWEEN | Outside a range | `year NOT BETWEEN 2000 AND 2010` |
| IN | Exists in a list | `id IN (1, 2, 3)` |
| NOT IN | Not in a list | `id NOT IN (1, 2, 3)` |

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
| 8 | Ratatouille | Brad Bird | 2007 | 115 |
| 9 | WALL-E | Andrew Stanton | 2008 | 104 |
| 10 | Up | Pete Docter | 2009 | 101 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |
| 12 | Cars 2 | John Lasseter | 2011 | 120 |
| 13 | Brave | Brenda Chapman | 2012 | 102 |
| 14 | Monsters University | Dan Scanlon | 2013 | 110 |

---

# ✅ Exercise Solutions

---

## 1️⃣ Find the movie with a row id of 6

### Query

```sql
SELECT *
FROM movies
WHERE id = 6;
```

### Explanation

- `WHERE id = 6` filters the table
- Only the movie with id 6 is returned

### Output

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 6 | The Incredibles | Brad Bird | 2004 | 116 |

---

## 2️⃣ Find the movies released in the years between 2000 and 2010

### Query

```sql
SELECT *
FROM movies
WHERE year BETWEEN 2000 AND 2010;
```

### Explanation

`BETWEEN` includes both starting and ending values.

This retrieves movies released from 2000 through 2010.

---

## 3️⃣ Find the movies NOT released in the years between 2000 and 2010

### Query

```sql
SELECT *
FROM movies
WHERE year NOT BETWEEN 2000 AND 2010;
```

### Explanation

This excludes movies released between 2000 and 2010.

Only older or newer movies are returned.

---

## 4️⃣ Find the first 5 Pixar movies and their release year

### Query

```sql
SELECT title, year
FROM movies
WHERE id IN (1, 2, 3, 4, 5);
```

### Explanation

`IN` checks whether a value exists inside a list.

This retrieves the first 5 movies based on their ids.

---

# 🎯 Key Takeaways

- `WHERE` filters rows
- `AND` combines multiple conditions
- `BETWEEN` checks ranges
- `IN` checks values inside a list
- Constraints make queries faster and cleaner

---

# 📌 Quick Revision

| Purpose | Query Example |
|---|---|
| Filter rows | `WHERE id = 1` |
| Multiple conditions | `WHERE year >= 2000 AND year <= 2010` |
| Range filtering | `WHERE year BETWEEN 2000 AND 2010` |
| Excluding range | `WHERE year NOT BETWEEN 2000 AND 2010` |
| Value list | `WHERE id IN (1,2,3)` |

---

# 🚀 Practice Queries

```sql
SELECT *
FROM movies
WHERE year > 2005;

SELECT title
FROM movies
WHERE director = 'Brad Bird';

SELECT *
FROM movies
WHERE year BETWEEN 1995 AND 2005;

SELECT title, year
FROM movies
WHERE id IN (1, 3, 5);

SELECT *
FROM movies
WHERE year NOT BETWEEN 2000 AND 2010;
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ How to filter rows using `WHERE`  
✅ How to apply conditions using operators  
✅ How to use `BETWEEN` and `NOT BETWEEN`  
✅ How to use `IN` for matching lists  
✅ How constraints improve query efficiency

---

# 🏁 End of Lesson 2
