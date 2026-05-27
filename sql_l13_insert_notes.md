# SQLBolt - Lesson 13: Inserting Rows

# 📘 Introduction

Until now, we only learned how to read data using SELECT queries.

Now we learn how to ADD new data into tables.

SQL uses:

# 🔥 INSERT

---

# 🧠 What is a Schema?

A schema defines:

- table structure
- column names
- data types

Example:

| Column | Data Type |
|---|---|
| year | Integer |
| title | String/Text |

---

# 🎯 Why Schemas Matter

Schemas ensure:

- correct data storage
- consistency
- database efficiency

---

# ⭐ INSERT Statement

INSERT adds new rows into a table.

---

# 🧠 Basic INSERT Syntax

```sql
INSERT INTO table_name
VALUES (value1, value2, value3);
```

---

# ⭐ INSERT with Specific Columns

```sql
INSERT INTO table_name
(column1, column2)
VALUES (value1, value2);
```

---

# 🧠 Why Specify Columns?

Benefits:

- safer
- easier to read
- future-proof
- works even if table changes later

---

# ⭐ Multiple Row Insert

```sql
INSERT INTO movies
(title, year)
VALUES
('Movie1', 2020),
('Movie2', 2021);
```

---

# ⭐ INSERT with Expressions

You can also calculate values during insertion.

## Example

```sql
INSERT INTO boxoffice
(movie_id, sales_in_millions)
VALUES (1, 300000000 / 1000000);
```

---

# 📂 Movies Table

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |

---

# 📂 BoxOffice Table

| movie_id | rating | domestic_sales | international_sales |
|---|---|---|---|
| 3 | 7.9 | 245852179 | 239163000 |
| 1 | 8.3 | 191796233 | 170162503 |
| 2 | 7.2 | 162798565 | 200600000 |

---

# ✅ Exercise Solutions

---

# 1️⃣ Add Toy Story 4 to Movies table

## Query

```sql
INSERT INTO movies
(title, director, year, length_minutes)
VALUES ('Toy Story 4', 'Josh Cooley', 2019, 100);
```

---

## 🧠 Explanation

### INSERT INTO movies

chooses movies table.

---

### Specified columns

```sql
(title, director, year, length_minutes)
```

tells SQL which columns receive values.

---

### VALUES(...)

contains inserted data.

---

# ⚠️ Why id is missing?

Because:

```text
id is auto-incrementing
```

Database automatically creates it.

---

# 2️⃣ Add BoxOffice record for Toy Story 4

## Query

```sql
INSERT INTO boxoffice
(movie_id, rating, domestic_sales, international_sales)
VALUES (15, 8.7, 340000000, 270000000);
```

---

## 🧠 Explanation

### movie_id = 15

matches newly inserted movie.

---

### rating = 8.7

stores movie rating.

---

### domestic_sales

US sales.

---

### international_sales

outside-US sales.

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| INSERT INTO | choose table |
| VALUES | inserted data |
| Schema | table structure |
| Auto Increment | automatic IDs |
| Expressions | calculations inside INSERT |

---

# 🔥 Most Important Understanding

## Full Insert

```sql
INSERT INTO movies
VALUES (...);
```

requires ALL column values.

---

## Safer Insert

```sql
INSERT INTO movies
(title, year)
VALUES (...);
```

specifies exact columns.

This is preferred.

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Insert full row | `INSERT INTO table VALUES (...)` |
| Insert selected columns | `INSERT INTO table(col1, col2)` |
| Insert multiple rows | multiple VALUES |
| Insert calculated value | use expressions |

---

# 🚀 Practice Queries

```sql
INSERT INTO movies
(title, director, year, length_minutes)
VALUES ('Inside Out', 'Pete Docter', 2015, 95);

INSERT INTO movies
(title, director)
VALUES ('Coco', 'Lee Unkrich');

INSERT INTO boxoffice
(movie_id, rating, domestic_sales, international_sales)
VALUES (16, 8.5, 200000000, 300000000);

INSERT INTO movies
(title, year)
VALUES
('Movie A', 2020),
('Movie B', 2021);
```

---

# 📚 What You Learned

By completing this lesson, you now understand:

✅ What schemas are  
✅ How INSERT works  
✅ How to add rows into tables  
✅ How to insert into specific columns  
✅ How auto-increment IDs work  
✅ How expressions work inside INSERT

---

# 🏁 End of Lesson 13
