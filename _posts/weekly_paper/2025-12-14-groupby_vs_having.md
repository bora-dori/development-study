---
layout: post
title: "SQL - GROUP BY vs HAVING"
date: 2025-12-14 +0900
---
# Understanding GROUP BY and HAVING in SQL 🧩

`GROUP BY` and `HAVING` are essential SQL clauses used for summarizing and filtering aggregated data.  
They look similar at first, but they operate at **different stages** and serve **different purposes** in a query.  
This guide explains both clauses clearly and shows when each one should be used.

---

## 1. What GROUP BY Does

The `GROUP BY` clause groups rows based on the values of one or more columns.  
This grouping step is required when applying aggregate functions such as `SUM`, `AVG`, `COUNT`, `MAX`, and `MIN`.

**Purpose:** 
- **Creates groups:** Rows with identical values in specified columns form one logical group.
- **Defines aggregation units:** Without grouping, aggregates operate on the entire table; with grouping, aggregates operate *per group*.

**Example:**  
- Group customers by country to calculate metrics per region.  
- Group products by category to summarize sales or counts.

`GROUP BY` transforms row-level data into meaningful summary-level insights.

---

## 2. What HAVING Does

`HAVING` filters **aggregated results**.  
It is applied after the data has been grouped and aggregate functions have been calculated.

**Purpose:** 
- **Filters groups** based on aggregate conditions.
- **Allows aggregate functions** (unlike the `WHERE` clause).
- Determines which summary groups appear in the final output.

**Example:**
- Keep only groups with more than 5 rows.  
- Keep groups whose average price is below a certain value.

`HAVING` is essential when filtering must be done on aggregated values rather than raw rows.

---

## 3. WHERE vs HAVING

Understanding SQL’s logical execution order makes the difference clear:

| Clause | When It Runs | Applies To | Allows Aggregates? | Purpose |
|--------|--------------|------------|---------------------|---------|
| **WHERE** | Before grouping | Individual rows | No | Filters raw data before grouping |
| **HAVING** | After grouping | Aggregated groups | Yes | Filters summary results |

If the condition uses an aggregate function, it **must** be in `HAVING`, not `WHERE`.

---

## Summary

A typical analytical SQL workflow follows this order:

1. **WHERE** filters the original dataset.  
2. **GROUP BY** groups the filtered rows.  
3. **Aggregate functions** compute summary values for each group.  
4. **HAVING** filters those summary results.  
5. **SELECT** returns the final grouped and filtered output.

Understanding this flow is key for writing accurate SQL queries.
