# SQLBolt - Lesson 1: SELECT Queries 101

## 📘 Introduction

To retrieve data from a SQL database, we use **SELECT statements**.

A SQL query tells the database:

- What data we want
- Which table to get it from
- Which columns to display

Think of a SQL table like this:

| Concept | Example |
|---|---|
| Table | Movies |
| Row | One movie |
| Column | Title, Director, Year |

---

# 🧠 Basic SELECT Syntax

## Selecting Specific Columns

```sql
SELECT column_name
FROM table_name;
```

### Example

```sql
SELECT title
FROM movies;
```

This retrieves only the `title` column from the `movies` table.

---

# ⭐ Selecting Multiple Columns

```sql
SELECT column1, column2
FROM table_name;
```

### Example

```sql
SELECT title, director
FROM movies;
```

This returns:

| title | director |
|---|---|
| Toy Story | John Lasseter |
| Finding Nemo | Andrew Stanton |
| Up | Pete Docter |

---

# 🌟 Selecting All Columns

```sql
SELECT *
FROM table_name;
```

The `*` means:

> "Select everything"

### Example

```sql
SELECT *
FROM movies;
```

This displays the complete table.

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

## 1️⃣ Find the title of each film

### Query

```sql
SELECT title
FROM movies;
```

### Explanation

- `SELECT title` → choose the title column
- `FROM movies` → get data from the movies table

---

## 2️⃣ Find the director of each film

### Query

```sql
SELECT director
FROM movies;
```

### Explanation

This returns all movie directors.

---

## 3️⃣ Find the title and director of each film

### Query

```sql
SELECT title, director
FROM movies;
```

### Explanation

This retrieves two columns together.

---

## 4️⃣ Find the title and year of each film

### Query

```sql
SELECT title, year
FROM movies;
```

### Explanation

Useful when you want movie names along with release years.

---

## 5️⃣ Find all information about each film

### Query

```sql
SELECT *
FROM movies;
```

### Explanation

The `*` wildcard selects every column in the table.

---

# 🎯 Key Takeaways

- `SELECT` is used to retrieve data
- `FROM` specifies the table
- Multiple columns are separated using commas
- `*` selects all columns

---

# 📌 Quick Revision

| Query Type | Syntax |
|---|---|
| Single column | `SELECT column FROM table;` |
| Multiple columns | `SELECT col1, col2 FROM table;` |
| All columns | `SELECT * FROM table;` |

---

# 🚀 Practice Queries

```sql
SELECT title FROM movies;

SELECT year FROM movies;

SELECT title, year FROM movies;

SELECT director, year FROM movies;

SELECT * FROM movies;
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ How to retrieve data from a table  
✅ How to select specific columns  
✅ How to select multiple columns  
✅ How to retrieve the full table using `*`

---

# 🏁 End of Lesson 1
