# SQL Complete Notes (SQLBolt Lessons 1–18)

# 1. SELECT
Retrieve data from tables.

```sql
SELECT column1, column2
FROM table_name;
```

```sql
SELECT *
FROM table_name;
```

Key ideas:
- Rows = records
- Columns = attributes
- `*` = all columns

---

# 2. WHERE (Filtering)

```sql
SELECT *
FROM movies
WHERE year > 2000;
```

Operators:
- `=` Equal
- `!=`, `<>` Not equal
- `>`, `<`, `>=`, `<=`
- `BETWEEN`
- `IN`
- `NOT IN`

Examples:

```sql
WHERE year BETWEEN 2000 AND 2010
```

```sql
WHERE id IN (1,2,3)
```

---

# 3. Text Filtering

```sql
WHERE title LIKE 'Toy%'
```

Wildcards:

| Symbol | Meaning |
|----------|----------|
| % | Any number of characters |
| _ | One character |

Examples:

```sql
LIKE 'Toy%'
LIKE '%Story%'
LIKE '_ars'
```

---

# 4. DISTINCT

Remove duplicates.

```sql
SELECT DISTINCT director
FROM movies;
```

---

# 5. ORDER BY

```sql
SELECT *
FROM movies
ORDER BY year ASC;
```

```sql
ORDER BY rating DESC;
```

ASC = ascending
DESC = descending

---

# 6. LIMIT & OFFSET

```sql
SELECT *
FROM movies
LIMIT 5;
```

```sql
LIMIT 5 OFFSET 5;
```

Used for pagination.

---

# 7. JOINs

## INNER JOIN

Returns matching rows.

```sql
SELECT m.title, b.rating
FROM movies m
INNER JOIN boxoffice b
ON m.id = b.movie_id;
```

Workflow:
1. Identify required columns
2. Identify tables
3. Find common key
4. JOIN tables
5. Filter / sort

---

## LEFT JOIN

Keeps all rows from left table.

```sql
SELECT *
FROM buildings b
LEFT JOIN employees e
ON b.name = e.building;
```

Used for:
- finding missing matches
- finding empty buildings

```sql
WHERE e.building IS NULL;
```

---

# 8. NULL

NULL means:
- missing
- unknown
- not assigned

Correct:

```sql
WHERE building IS NULL
```

```sql
WHERE building IS NOT NULL
```

Wrong:

```sql
WHERE building = NULL
```

---

# 9. Expressions

```sql
SELECT rating * 10 AS rating_percent
FROM boxoffice;
```

```sql
SELECT domestic_sales + international_sales
FROM boxoffice;
```

Aliases:

```sql
AS alias_name
```

---

# 10. Aggregate Functions

## COUNT

```sql
SELECT COUNT(*)
FROM employees;
```

## MAX

```sql
SELECT MAX(years_employed)
FROM employees;
```

## MIN

```sql
SELECT MIN(years_employed)
FROM employees;
```

## AVG

```sql
SELECT AVG(years_employed)
FROM employees;
```

## SUM

```sql
SELECT SUM(years_employed)
FROM employees;
```

---

# 11. GROUP BY

```sql
SELECT role, COUNT(*)
FROM employees
GROUP BY role;
```

Creates groups before applying aggregate functions.

---

# 12. HAVING

Filters groups.

```sql
SELECT role, COUNT(*)
FROM employees
GROUP BY role
HAVING COUNT(*) > 3;
```

Difference:

| WHERE | HAVING |
|---------|---------|
| Filters rows | Filters groups |

---

# 13. Query Execution Order

Real SQL execution order:

1. FROM
2. JOIN
3. WHERE
4. GROUP BY
5. HAVING
6. SELECT
7. DISTINCT
8. ORDER BY
9. LIMIT/OFFSET

Most important interview topic.

---

# 14. INSERT

```sql
INSERT INTO movies
(title, director, year)
VALUES
('Toy Story 4', 'Josh Cooley', 2019);
```

Multiple rows:

```sql
INSERT INTO movies(title)
VALUES ('A'), ('B');
```

---

# 15. UPDATE

```sql
UPDATE movies
SET director='John Lasseter'
WHERE id=2;
```

Multiple columns:

```sql
UPDATE movies
SET title='Toy Story 3',
director='Lee Unkrich'
WHERE id=11;
```

Always use WHERE.

---

# 16. DELETE

```sql
DELETE FROM movies
WHERE year < 2005;
```

Danger:

```sql
DELETE FROM movies;
```

Deletes all rows.

---

# 17. CREATE TABLE

```sql
CREATE TABLE movies (
    id INTEGER PRIMARY KEY,
    title TEXT,
    year INTEGER
);
```

Common Types:
- INTEGER
- REAL/FLOAT
- TEXT
- BOOLEAN
- DATE

Constraints:
- PRIMARY KEY
- UNIQUE
- NOT NULL
- CHECK
- FOREIGN KEY

---

# 18. ALTER TABLE

Add column:

```sql
ALTER TABLE movies
ADD Language TEXT DEFAULT 'English';
```

Rename:

```sql
ALTER TABLE movies
RENAME TO films;
```

---

# 19. DROP TABLE

```sql
DROP TABLE IF EXISTS movies;
```

Difference:

DELETE = removes rows

DROP = removes table

---

# SQL Problem Solving Workflow

1. Understand question
2. Find required columns
3. Find required table(s)
4. Check if JOIN needed
5. Filter using WHERE
6. Group if aggregate required
7. Filter groups using HAVING
8. Sort using ORDER BY
9. Limit results if needed

---

# Most Important Interview Concepts

- SELECT
- WHERE
- LIKE
- ORDER BY
- LIMIT
- INNER JOIN
- LEFT JOIN
- NULL
- GROUP BY
- HAVING
- Aggregate Functions
- Query Execution Order
- INSERT
- UPDATE
- DELETE
- CREATE TABLE
- ALTER TABLE
- DROP TABLE
