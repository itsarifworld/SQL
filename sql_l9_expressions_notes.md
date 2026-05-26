# SQLBolt - Lesson 9: Queries with Expressions

# 📘 Introduction

SQL expressions allow us to:

- perform calculations
- transform data
- combine values
- create custom outputs

Expressions make queries more powerful.

---

# 🧠 What is an Expression?

An expression is a calculation inside a SQL query.

Example:

```sql
SELECT salary * 12
FROM employees;
```

This calculates yearly salary.

---

# ⭐ AS Keyword (Aliases)

Aliases rename columns or tables.

## Example

```sql
SELECT salary * 12 AS yearly_salary
FROM employees;
```

`AS yearly_salary` changes the output column name.

---

# ⭐ Table Aliases

```sql
SELECT m.title
FROM movies AS m;
```

Here:

```text
movies = m
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

---

# 📂 BoxOffice Table

| movie_id | rating | domestic_sales | international_sales |
|---|---|---|---|
| 5 | 8.2 | 380843261 | 555900000 |
| 3 | 7.9 | 245852179 | 239163000 |
| 1 | 8.3 | 191796233 | 170162503 |

---

# ✅ Exercise Solutions

# 1️⃣ List all movies and their combined sales in millions of dollars

## Query

```sql
SELECT title,
       (domestic_sales + international_sales) / 1000000 AS sales_in_millions
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id;
```

---

## 🧠 Explanation

```sql
domestic_sales + international_sales
```

adds total sales.

---

```sql
/ 1000000
```

converts into millions.

---

# 2️⃣ List all movies and their ratings in percent

## Query

```sql
SELECT title,
       rating * 10 AS rating_percent
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id;
```

---

## 🧠 Explanation

Ratings are out of 10.

Example:

```text
8.3 × 10 = 83%
```

---

# 3️⃣ List all movies released on even-numbered years

## Query

```sql
SELECT title, year
FROM movies
WHERE MOD(year, 2) = 0;
```

---

## 🧠 Explanation

```sql
MOD(year, 2)
```

finds remainder after dividing by 2.

Even numbers give remainder 0.

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| Expression | calculation inside query |
| + | addition |
| * | multiplication |
| / | division |
| AS | alias/rename |
| MOD() | remainder |

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Add values | `col1 + col2` |
| Multiply values | `rating * 10` |
| Rename output | `AS alias` |
| Even number check | `MOD(col, 2) = 0` |

---

# 📚 What You Learned

✅ How SQL expressions work  
✅ How to perform calculations  
✅ How aliases work  
✅ How to transform outputs  
✅ How to check even numbers

---

# 🏁 End of Lesson 9
