# SQL Quick Revision Sheet

## Query Structure

```sql
SELECT columns
FROM table
WHERE condition
GROUP BY column
HAVING condition
ORDER BY column
LIMIT n;
```

---

## Filtering

```sql
WHERE age > 18
WHERE id IN (1,2,3)
WHERE year BETWEEN 2000 AND 2010
```

---

## LIKE

```sql
LIKE 'Toy%'
LIKE '%Story%'
LIKE '_ars'
```

% = many chars
_ = one char

---

## Sorting

```sql
ORDER BY year ASC
ORDER BY rating DESC
```

---

## Pagination

```sql
LIMIT 5
LIMIT 5 OFFSET 5
```

---

## JOIN

```sql
INNER JOIN table2
ON table1.id = table2.id
```

```sql
LEFT JOIN table2
ON table1.id = table2.id
```

---

## NULL

```sql
IS NULL
IS NOT NULL
```

---

## Aggregates

```sql
COUNT(*)
SUM(col)
AVG(col)
MIN(col)
MAX(col)
```

---

## GROUP BY

```sql
GROUP BY role
```

---

## HAVING

```sql
HAVING COUNT(*) > 3
```

---

## INSERT

```sql
INSERT INTO table(col1,col2)
VALUES(val1,val2);
```

---

## UPDATE

```sql
UPDATE table
SET col=value
WHERE condition;
```

---

## DELETE

```sql
DELETE FROM table
WHERE condition;
```

---

## CREATE TABLE

```sql
CREATE TABLE students(
 id INTEGER PRIMARY KEY,
 name TEXT
);
```

---

## ALTER TABLE

```sql
ALTER TABLE students
ADD age INTEGER;
```

---

## DROP TABLE

```sql
DROP TABLE students;
```

---

## Execution Order

FROM
→ JOIN
→ WHERE
→ GROUP BY
→ HAVING
→ SELECT
→ DISTINCT
→ ORDER BY
→ LIMIT

---

## Golden Rule

Always:
1. SELECT first
2. Test conditions
3. Then UPDATE or DELETE
