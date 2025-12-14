---
layout: post
title: "Understanding NULL in SQL"
date: 2025-12-14 +0900
---
# What NULL Means in SQL and How to Work With It ❌

In SQL, `NULL` represents **the absence of a value**.  
It does *not* mean zero, and it does *not* mean an empty string — it literally means “unknown.”

Because of this, SQL treats `NULL` differently from any other value, and special functions are required to work with it properly.

---

## 1. What NULL Is (and Is Not)

- `NULL` means **missing**, **undefined**, or **not applicable**
- `NULL` ≠ `0`
- `NULL` ≠ `''` (empty string)

Examples:
- `NULL = NULL` → `NULL`  
- `NULL > 5` → `NULL`  
- `NULL + 3` → `NULL`

This is why queries involving `NULL` behave differently from regular values.

---

## 2. Checking for NULL

Because `=` does not work with `NULL`, SQL provides:

- `IS NULL`
- `IS NOT NULL`

These are the only safe ways to test missing values.

---

## 3. Functions for Handling NULL

SQL offers several functions for replacing or managing NULL values.

**1. `COALESCE(a, b, c, ...)`**
Returns the first non-NULL value in the list.  
It is the most flexible and widely used NULL-handling function.

**2. `IFNULL(a, b)` (MySQL)**
Returns `b` if `a` is NULL.

**3. `NULLIF(a, b)`**
Returns NULL if `a` equals `b`; otherwise returns `a`.

Useful for preventing division-by-zero errors.

**Aggregations and NULL:**
Aggregate functions like `SUM`, `COUNT`, `AVG` normally **ignore NULL values**, except for:
- `COUNT(*)` which counts rows regardless of NULLs.

---

## Summary

- `NULL` represents “unknown” or “missing” data  
- It is not equal to zero or an empty string  
- Use `IS NULL` and `IS NOT NULL` for comparisons  
- Use functions like `COALESCE`, `IFNULL`, and `NULLIF` to handle NULL safely  
- Aggregate functions typically skip NULL values  

Handling NULL correctly is essential for accurate SQL queries and reliable analytics.
