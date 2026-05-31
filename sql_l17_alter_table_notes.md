# SQLBolt - Lesson 17: Altering Tables

# 📘 Introduction

Databases evolve over time.

You may need to:

- Add new columns
- Remove old columns
- Rename tables
- Change table structure

SQL provides:

# 🔥 ALTER TABLE

to modify existing tables.

---

# 🧠 Why ALTER TABLE?

Suppose your Movies table originally has:

```text
id | title | director
```

Later you want to store:

```text
language
aspect_ratio
budget
```

Instead of creating a new table, you modify the existing one.

---

# ⭐ Add a New Column

```sql
ALTER TABLE movies
ADD language TEXT;
```

This adds a new column to all rows.

---

# ⭐ Add a Column with Default Value

```sql
ALTER TABLE movies
ADD language TEXT DEFAULT 'English';
```

Existing and future rows get English by default.

---

# ⭐ Remove a Column

```sql
ALTER TABLE movies
DROP language;
```

⚠️ Not supported in some databases like older SQLite versions.

---

# ⭐ Rename a Table

```sql
ALTER TABLE movies
RENAME TO pixar_movies;
```

Changes table name.

---

# 📂 Exercise Tasks

## Task 1
Add a column named Aspect_ratio with FLOAT datatype.

### Solution

```sql
ALTER TABLE movies
ADD Aspect_ratio FLOAT;
```

### Explanation

- ALTER TABLE → modify table
- ADD → add new column
- Aspect_ratio → column name
- FLOAT → decimal values like 1.85, 2.39

---

## Task 2
Add a column named Language with TEXT datatype and default English.

### Solution

```sql
ALTER TABLE movies
ADD Language TEXT DEFAULT 'English';
```

### Explanation

- Language stores movie language
- TEXT stores strings
- DEFAULT 'English' automatically fills missing values

---

# 🎯 Key Concepts

| Concept | Meaning |
|----------|----------|
| ALTER TABLE | modify existing table |
| ADD | add new column |
| DROP | remove column |
| RENAME TO | rename table |
| DEFAULT | automatic value |
| FLOAT | decimal numbers |
| TEXT | strings |

---

# ⚠️ Common Mistakes

### Forgetting Data Type

❌

```sql
ALTER TABLE movies
ADD Language;
```

✅

```sql
ALTER TABLE movies
ADD Language TEXT;
```

---

### Wrong Default Value Syntax

❌

```sql
DEFAULT English
```

✅

```sql
DEFAULT 'English'
```

---

# 📌 Quick Revision

```sql
ALTER TABLE movies
ADD rating FLOAT;
```

```sql
ALTER TABLE movies
ADD language TEXT DEFAULT 'English';
```

```sql
ALTER TABLE movies
RENAME TO films;
```

---

# 📚 What You Learned

✅ How ALTER TABLE works

✅ How to add new columns

✅ How DEFAULT values work

✅ How to rename tables

✅ Basic schema modification

---

# 🏁 End of Lesson 17
