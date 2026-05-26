# SQLBolt - Lesson 3: Queries with Constraints (Pt. 2)

## 📘 Introduction

In SQL, text data can also be filtered using the `WHERE` clause.

SQL provides powerful operators for:

- String matching
- Pattern searching
- Wildcards
- Case-insensitive comparisons

These are extremely useful when working with names, titles, emails, categories, and more.

---

# 🧠 Basic Syntax

```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

---

# ⭐ Text Operators in SQL

| Operator | Meaning | Example |
|---|---|---|
| = | Exact string match | `title = "Toy Story"` |
| != or <> | Not equal | `director != "John Lasseter"` |
| LIKE | Case-insensitive matching | `title LIKE "toy story"` |
| NOT LIKE | Opposite of LIKE | `title NOT LIKE "Cars"` |
| % | Matches multiple characters | `title LIKE "%Story%"` |
| _ | Matches one character | `title LIKE "Toy Stor_"` |
| IN | Value exists in a list | `director IN ("Brad Bird", "Pete Docter")` |
| NOT IN | Value not in a list | `director NOT IN ("John Lasseter")` |

---

# 🔥 Wildcards Explained

## `%` Wildcard

Matches zero or more characters.

### Example

```sql
SELECT *
FROM movies
WHERE title LIKE "%Story%";
```

Matches:

- Toy Story
- Toy Story 2
- Toy Story 3

---

## `_` Wildcard

Matches exactly one character.

### Example

```sql
SELECT *
FROM movies
WHERE title LIKE "WALL-_";
```

Matches:

- WALL-E
- WALL-G

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
| 87 | WALL-G | Brenda Chapman | 2042 | 97 |

---

# ✅ Exercise Solutions

---

## 1️⃣ Find all the Toy Story movies

### Query

```sql
SELECT *
FROM movies
WHERE title LIKE "Toy Story%";
```

### Explanation

- `LIKE` is used for pattern matching
- `%` matches any characters after "Toy Story"

### Matches

- Toy Story
- Toy Story 2
- Toy Story 3

---

## 2️⃣ Find all the movies directed by John Lasseter

### Query

```sql
SELECT *
FROM movies
WHERE director = "John Lasseter";
```

### Explanation

This returns only movies where the director exactly matches John Lasseter.

---

## 3️⃣ Find all the movies (and director) not directed by John Lasseter

### Query

```sql
SELECT title, director
FROM movies
WHERE director != "John Lasseter";
```

### Explanation

- `!=` means "not equal to"
- Returns movies directed by everyone except John Lasseter

---

## 4️⃣ Find all the WALL-* movies

### Query

```sql
SELECT *
FROM movies
WHERE title LIKE "WALL-_";
```

### Explanation

- `_` matches exactly one character
- This matches both:
  - WALL-E
  - WALL-G

---

# 🎯 Key Takeaways

- `LIKE` is used for pattern matching
- `%` matches multiple characters
- `_` matches a single character
- `=` checks exact matches
- `!=` excludes specific values

---

# 📌 Quick Revision

| Purpose | Query Example |
|---|---|
| Exact match | `WHERE director = "Brad Bird"` |
| Not equal | `WHERE director != "John Lasseter"` |
| Starts with | `WHERE title LIKE "Toy%"` |
| Ends with | `WHERE title LIKE "%Story"` |
| Contains | `WHERE title LIKE "%Story%"` |
| Single character wildcard | `WHERE title LIKE "WALL-_"` |

---

# 🚀 Practice Queries

```sql
SELECT *
FROM movies
WHERE title LIKE "%Cars%";

SELECT *
FROM movies
WHERE director = "Pete Docter";

SELECT title, year
FROM movies
WHERE title LIKE "%Story%";

SELECT *
FROM movies
WHERE title LIKE "WALL-_";

SELECT *
FROM movies
WHERE director != "Brad Bird";
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ How to filter text data  
✅ How to use `LIKE` for pattern matching  
✅ How wildcards `%` and `_` work  
✅ How to compare strings in SQL  
✅ How to search using flexible text patterns

---

# 🏁 End of Lesson 3
