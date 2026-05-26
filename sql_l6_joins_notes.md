# SQLBolt - Lesson 6: Multi-table Queries with JOINs

# 📘 Introduction

Until now, we worked with only one table at a time.

But real databases usually store related data in multiple tables.

To combine data from multiple tables, SQL uses:

# 🔥 JOINs

---

# 🧠 Why Multiple Tables?

Suppose we have:

## Movies Table

| id | title |
|---|---|
| 1 | Toy Story |

---

## BoxOffice Table

| movie_id | rating |
|---|---|
| 1 | 8.3 |

Instead of storing everything in one giant table, databases separate information into smaller organized tables.

This is called:

# Database Normalization

---

# 🎯 What is Normalization?

Normalization means:

- reducing duplicate data
- organizing related data into separate tables
- making databases efficient and scalable

---

# 🧠 What is a JOIN?

A JOIN combines rows from two tables using a common column.

In this lesson:

movies.id = boxoffice.movie_id

These matching columns connect both tables.

---

# ⭐ INNER JOIN

INNER JOIN returns only rows that match in both tables.

---

# 🧠 INNER JOIN Syntax

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.id = table2.id;
```

---

# 🔥 Easy Mental Model

JOIN = connect tables using common columns

---

# ✅ Exercise Solutions

# 1️⃣ Find the domestic and international sales for each movie

## Query

```sql
SELECT title, domestic_sales, international_sales
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id;
```

---

# 2️⃣ Show sales numbers for movies that did better internationally

## Query

```sql
SELECT title, domestic_sales, international_sales
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
WHERE international_sales > domestic_sales;
```

---

# 3️⃣ List all movies by ratings in descending order

## Query

```sql
SELECT title, rating
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
ORDER BY rating DESC;
```

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| JOIN | combine tables |
| INNER JOIN | keep matching rows only |
| ON | matching condition |
| ORDER BY DESC | highest to lowest |

---

# 📚 What You Learned

✅ How INNER JOIN works  
✅ How tables are connected using keys  
✅ How to combine data from multiple tables  
✅ How to filter joined data  
✅ How to sort joined results

---

# 🏁 End of Lesson 6
