# SQLBolt - Lesson 18: Dropping Tables

# 📘 Introduction

So far we learned how to:

- CREATE tables
- INSERT rows
- UPDATE rows
- DELETE rows
- ALTER tables

Now we learn how to completely remove a table from a database.

SQL uses:

# 🔥 DROP TABLE

---

# 🧠 What is DROP TABLE?

`DROP TABLE` removes:

✅ All rows (data)

✅ Table structure (schema)

✅ Constraints

✅ Metadata

After dropping a table, it no longer exists in the database.

---

# ⭐ DROP TABLE Syntax

```sql
DROP TABLE table_name;
```

---

# ⭐ Safe Syntax

```sql
DROP TABLE IF EXISTS table_name;
```

This avoids errors if the table does not exist.

---

# ⚠️ Difference Between DELETE and DROP

| DELETE | DROP |
|----------|----------|
| Removes rows | Removes entire table |
| Table remains | Table disappears |
| Schema remains | Schema removed |
| Can use WHERE | No WHERE clause |

---

## Example: DELETE

```sql
DELETE FROM movies;
```

Result:

```text
Movies table exists
But contains no rows
```

---

## Example: DROP

```sql
DROP TABLE movies;
```

Result:

```text
Movies table no longer exists
```

---

# ⚠️ Foreign Key Considerations

Suppose:

```text
employees
```

depends on:

```text
departments
```

using a FOREIGN KEY.

You may need to:

- remove dependent rows first
- drop dependent tables first

before dropping the main table.

---

# ✅ Exercise Solutions

## Task 1

Remove the Movies table.

### Query

```sql
DROP TABLE IF EXISTS movies;
```

### Explanation

- DROP TABLE removes table completely
- IF EXISTS prevents errors

---

## Task 2

Remove the BoxOffice table.

### Query

```sql
DROP TABLE IF EXISTS boxoffice;
```

### Explanation

Removes the entire BoxOffice table and its schema.

---

# 🎯 Key Concepts

| Concept | Meaning |
|----------|----------|
| DROP TABLE | remove entire table |
| IF EXISTS | avoid errors |
| DELETE | remove rows only |
| Schema | table structure |
| Foreign Key | table dependency |

---

# 🔥 Most Important Understanding

### DELETE

```sql
DELETE FROM movies;
```

After execution:

```text
Movies table exists
0 rows
```

---

### DROP

```sql
DROP TABLE movies;
```

After execution:

```text
Movies table does not exist
```

---

# ⚠️ Common Mistakes

### Mistake 1

```sql
DROP TABLE movies;
```

without checking dependencies.

Can break related tables.

---

### Mistake 2

Confusing DELETE with DROP.

DELETE removes data.

DROP removes the entire table.

---

# 📌 Quick Revision

```sql
DROP TABLE movies;
```

```sql
DROP TABLE IF EXISTS movies;
```

```sql
DELETE FROM movies;
```

Remember:

```text
DELETE -> remove rows
DROP -> remove table
```

---

# 📚 What You Learned

✅ How DROP TABLE works

✅ Difference between DELETE and DROP

✅ Why IF EXISTS is useful

✅ What happens to schema when dropping a table

✅ Basic database cleanup operations

---

# 🏁 End of Lesson 18 (SQLBolt Complete!)
