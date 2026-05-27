# SQLBolt - Lesson 12: Order of Execution of a Query

# 📘 Introduction

SQL queries are written in one order but executed in another order internally.

Understanding execution order is very important.

---

# 🧠 Real Order of Execution

| Step | Clause |
|---|---|
| 1 | FROM + JOIN |
| 2 | WHERE |
| 3 | GROUP BY |
| 4 | HAVING |
| 5 | SELECT |
| 6 | DISTINCT |
| 7 | ORDER BY |
| 8 | LIMIT / OFFSET |

---

# 1️⃣ FROM and JOIN

SQL first gathers data from tables.

## Example

```sql
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
```

This creates a combined working table.

---

# 2️⃣ WHERE

Filters rows before grouping.

## Example

```sql
WHERE year > 2000
```

---

# 3️⃣ GROUP BY

Creates groups from remaining rows.

## Example

```sql
GROUP BY director
```

---

# 4️⃣ HAVING

Filters grouped rows.

## Example

```sql
HAVING COUNT(*) > 2
```

---

# 5️⃣ SELECT

Computes final output columns.

---

# 6️⃣ DISTINCT

Removes duplicate rows.

---

# 7️⃣ ORDER BY

Sorts rows.

## Example

```sql
ORDER BY rating DESC
```

---

# 8️⃣ LIMIT / OFFSET

Restricts final rows.

---

# ✅ Exercise Solutions

# 1️⃣ Find the number of movies each director has directed

## Query

```sql
SELECT director,
       COUNT(*) AS movie_count
FROM movies
GROUP BY director;
```

---

## 🧠 Explanation

```sql
GROUP BY director
```

creates groups for each director.

---

```sql
COUNT(*)
```

counts movies inside each group.

---

# 2️⃣ Find total domestic and international sales for each director

## Query

```sql
SELECT director,
       SUM(domestic_sales) AS total_domestic_sales,
       SUM(international_sales) AS total_international_sales
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
GROUP BY director;
```

---

## 🧠 Explanation

### JOIN tables

```sql
INNER JOIN boxoffice
```

combines movie and sales data.

---

### GROUP BY director

creates director groups.

---

### SUM()

adds sales values for each director.

---

# 🎯 Key Concepts

| Concept | Meaning |
|---|---|
| FROM | choose table |
| JOIN | combine tables |
| WHERE | filter rows |
| GROUP BY | create groups |
| HAVING | filter groups |
| SELECT | compute output |
| DISTINCT | remove duplicates |
| ORDER BY | sort rows |
| LIMIT | restrict rows |

---

# 📌 Quick Revision

| Clause | Purpose |
|---|---|
| FROM | get data |
| WHERE | filter rows |
| GROUP BY | create groups |
| HAVING | filter groups |
| ORDER BY | sorting |
| LIMIT | limit output |

---

# 📚 What You Learned

✅ Real SQL execution order  
✅ Difference between WHERE and HAVING  
✅ How GROUP BY works internally  
✅ How JOINs execute first  
✅ How SQL processes queries step-by-step

---

# 🏁 End of Lesson 12
