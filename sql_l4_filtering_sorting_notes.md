# SQLBolt - Lesson 4: Filtering and Sorting Query Results

## 📘 Introduction

In real databases, query results are often:

- Unordered
- Repeated
- Too large to read easily

SQL provides powerful tools to:

- Remove duplicates
- Sort results
- Limit returned rows

The main keywords introduced in this lesson are:

- `DISTINCT`
- `ORDER BY`
- `LIMIT`
- `OFFSET`

---

# 🧠 DISTINCT Keyword

`DISTINCT` removes duplicate values from query results.

## Syntax

```sql
SELECT DISTINCT column_name
FROM table_name;
```

### Example

```sql
SELECT DISTINCT director
FROM movies;
```

This returns each director only once.

---

# ⭐ ORDER BY Clause

`ORDER BY` sorts query results.

## Syntax

```sql
SELECT column1, column2
FROM table_name
ORDER BY column_name ASC;
```

### Sorting Types

| Keyword | Meaning |
|---|---|
| ASC | Ascending order |
| DESC | Descending order |

---

## Example: Ascending Order

```sql
SELECT title, year
FROM movies
ORDER BY year ASC;
```

Shows movies from oldest to newest.

---

## Example: Descending Order

```sql
SELECT title, year
FROM movies
ORDER BY year DESC;
```

Shows movies from newest to oldest.

---

# 🔥 LIMIT Clause

`LIMIT` restricts how many rows are returned.

## Syntax

```sql
SELECT *
FROM table_name
LIMIT number;
```

### Example

```sql
SELECT *
FROM movies
LIMIT 5;
```

Returns only the first 5 rows.

---

# 🚀 OFFSET Clause

`OFFSET` skips rows before starting to return results.

## Syntax

```sql
SELECT *
FROM table_name
LIMIT 5 OFFSET 5;
```

This skips the first 5 rows and returns the next 5.

---

# 📂 Movies Table

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Brave | Brenda Chapman | 2012 | 102 |
| 2 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 3 | Up | Pete Docter | 2009 | 101 |
| 4 | Monsters, Inc. | Pete Docter | 2001 | 92 |
| 5 | Toy Story | John Lasseter | 1995 | 81 |
| 6 | A Bug's Life | John Lasseter | 1998 | 95 |
| 7 | Monsters University | Dan Scanlon | 2013 | 110 |
| 8 | Ratatouille | Brad Bird | 2007 | 115 |
| 9 | Cars | John Lasseter | 2006 | 117 |
| 10 | WALL-E | Andrew Stanton | 2008 | 104 |
| 11 | Finding Nemo | Andrew Stanton | 2003 | 107 |
| 12 | The Incredibles | Brad Bird | 2004 | 116 |
| 13 | Cars 2 | John Lasseter | 2011 | 120 |
| 14 | Toy Story 3 | Lee Unkrich | 2010 | 103 |

---

# ✅ Exercise Solutions

---

## 1️⃣ List all directors of Pixar movies (alphabetically), without duplicates

### Query

```sql
SELECT DISTINCT director
FROM movies
ORDER BY director ASC;
```

### Explanation

- `DISTINCT` removes duplicate directors
- `ORDER BY director ASC` sorts alphabetically

---

## 2️⃣ List the last four Pixar movies released (ordered from most recent to least)

### Query

```sql
SELECT title, year
FROM movies
ORDER BY year DESC
LIMIT 4;
```

### Explanation

- `ORDER BY year DESC` sorts newest first
- `LIMIT 4` returns only four movies

---

## 3️⃣ List the first five Pixar movies sorted alphabetically

### Query

```sql
SELECT title
FROM movies
ORDER BY title ASC
LIMIT 5;
```

### Explanation

- Movies are sorted alphabetically
- Only first five are shown

---

## 4️⃣ List the next five Pixar movies sorted alphabetically

### Query

```sql
SELECT title
FROM movies
ORDER BY title ASC
LIMIT 5 OFFSET 5;
```

### Explanation

- `OFFSET 5` skips the first five rows
- `LIMIT 5` returns the next five rows

---

# 🎯 Key Takeaways

- `DISTINCT` removes duplicates
- `ORDER BY` sorts results
- `ASC` means ascending
- `DESC` means descending
- `LIMIT` restricts returned rows
- `OFFSET` skips rows

---

# 📌 Quick Revision

| Purpose | Query Example |
|---|---|
| Remove duplicates | `SELECT DISTINCT director FROM movies;` |
| Sort ascending | `ORDER BY title ASC` |
| Sort descending | `ORDER BY year DESC` |
| Limit rows | `LIMIT 5` |
| Skip rows | `OFFSET 5` |

---

# 🚀 Practice Queries

```sql
SELECT DISTINCT year
FROM movies
ORDER BY year ASC;

SELECT title, year
FROM movies
ORDER BY title ASC;

SELECT *
FROM movies
ORDER BY year DESC
LIMIT 3;

SELECT title
FROM movies
ORDER BY title ASC
LIMIT 5 OFFSET 5;

SELECT director
FROM movies
ORDER BY director ASC;
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ How to remove duplicate results using `DISTINCT`  
✅ How to sort query results using `ORDER BY`  
✅ Difference between `ASC` and `DESC`  
✅ How to limit results using `LIMIT`  
✅ How to paginate results using `OFFSET`

---

# 🏁 End of Lesson 4
