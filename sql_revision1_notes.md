# SQLBolt - Review 1: Simple SELECT Queries

## 📘 Introduction

This review combines everything learned so far:

- `SELECT`
- `WHERE`
- `ORDER BY`
- `LIMIT`
- `OFFSET`

You will use these concepts together to solve real SQL problems.

---

# 🧠 Main Query Structure

```sql
SELECT column1, column2
FROM table_name
WHERE condition
ORDER BY column ASC/DESC
LIMIT number OFFSET number;
```

---

# 📂 North American Cities Table

| city | country | population | latitude | longitude |
|---|---|---|---|---|
| Guadalajara | Mexico | 1500800 | 20.659699 | -103.349609 |
| Toronto | Canada | 2795060 | 43.653226 | -79.383184 |
| Houston | United States | 2195914 | 29.760427 | -95.369803 |
| New York | United States | 8405837 | 40.712784 | -74.005941 |
| Philadelphia | United States | 1553165 | 39.952584 | -75.165222 |
| Havana | Cuba | 2106146 | 23.054070 | -82.345189 |
| Mexico City | Mexico | 8555500 | 19.432608 | -99.133208 |
| Phoenix | United States | 1513367 | 33.448377 | -112.074037 |
| Los Angeles | United States | 3884307 | 34.052234 | -118.243685 |
| Ecatepec de Morelos | Mexico | 1742000 | 19.601841 | -99.050674 |
| Montreal | Canada | 1717767 | 45.501689 | -73.567256 |
| Chicago | United States | 2718782 | 41.878114 | -87.629798 |

---

# ✅ Exercise Solutions

---

## 1️⃣ List all the Canadian cities and their populations

### Query

```sql
SELECT city, population
FROM north_american_cities
WHERE country = "Canada";
```

### Explanation

- `WHERE country = "Canada"` filters only Canadian cities
- Displays city name and population

---

## 2️⃣ Order all the cities in the United States by latitude from north to south

### Query

```sql
SELECT city, latitude
FROM north_american_cities
WHERE country = "United States"
ORDER BY latitude DESC;
```

### Explanation

- Higher latitude means more north
- `DESC` sorts from highest to lowest latitude

---

## 3️⃣ List all the cities west of Chicago, ordered from west to east

### Query

```sql
SELECT city, longitude
FROM north_american_cities
WHERE longitude < -87.629798
ORDER BY longitude ASC;
```

### Explanation

- Chicago longitude is `-87.629798`
- More negative longitude means farther west
- `ASC` sorts from west to east

---

## 4️⃣ List the two largest cities in Mexico (by population)

### Query

```sql
SELECT city, population
FROM north_american_cities
WHERE country = "Mexico"
ORDER BY population DESC
LIMIT 2;
```

### Explanation

- Filters only Mexican cities
- Sorts by population from largest to smallest
- Returns only top 2

---

## 5️⃣ List the third and fourth largest cities (by population) in the United States and their population

### Query

```sql
SELECT city, population
FROM north_american_cities
WHERE country = "United States"
ORDER BY population DESC
LIMIT 2 OFFSET 2;
```

### Explanation

- Sorts U.S. cities by population
- `OFFSET 2` skips the first two largest cities
- `LIMIT 2` returns the next two cities

---

# 🎯 Key Concepts Used

| Concept | Purpose |
|---|---|
| SELECT | Choose columns |
| WHERE | Filter rows |
| ORDER BY | Sort rows |
| DESC | Largest to smallest |
| LIMIT | Return few rows |
| OFFSET | Skip rows |

---

# 🔥 Important Understanding

## Latitude

- Higher latitude → More north
- Lower latitude → More south

Example:

| City | Latitude |
|---|---|
| Montreal | 45.5 |
| Houston | 29.7 |

Montreal is more north.

---

## Longitude

- More negative longitude → More west

Example:

| City | Longitude |
|---|---|
| Los Angeles | -118 |
| Chicago | -87 |

Los Angeles is west of Chicago.

---

# 📌 Quick Revision

| Goal | Query Pattern |
|---|---|
| Filter country | `WHERE country = "Canada"` |
| Sort by population | `ORDER BY population DESC` |
| Get top rows | `LIMIT 2` |
| Skip rows | `OFFSET 2` |

---

# 🚀 Practice Queries

```sql
SELECT city
FROM north_american_cities
WHERE country = "Mexico";

SELECT city, population
FROM north_american_cities
ORDER BY population DESC;

SELECT city
FROM north_american_cities
ORDER BY latitude ASC;

SELECT city, longitude
FROM north_american_cities
ORDER BY longitude ASC;

SELECT city
FROM north_american_cities
LIMIT 5;
```

---

# 📚 What You Learned

By completing this review, you now understand:

✅ How to combine multiple SQL clauses  
✅ How to filter rows using `WHERE`  
✅ How to sort using `ORDER BY`  
✅ How to limit rows using `LIMIT`  
✅ How to skip rows using `OFFSET`  
✅ How to solve real SQL problems

---

# 🏁 End of SQL Review 1
