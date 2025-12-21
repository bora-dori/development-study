---
layout: post
title: "Core Components of Data Modeling"
date: 2025-12-21 +0900
---
# Core Components of Data Modeling: Entity, Attribute, and Relationship

Logical data modeling describes **what data the system needs and how that data is logically related**, independent of any specific database technology.  
At the heart of logical modeling are three core components: **Entity**, **Attribute**, and **Relationship**.

This post explains each component clearly, with simple examples.

---

![100518_0621_ERDiagramTu1](https://github.com/user-attachments/assets/1283b225-ffe5-4b3c-8f37-acabc6b0b988)

The diagram above shows a logical data model for a product management system.  
It illustrates how **entities**, **attributes**, and **relationships** work together in a normalized design.

---

## 1. Entities

Entities represent core business objects.  
In this model, each box corresponds to an entity.

Main entities in the diagram include:
- Product
- Color
- Category
- Apparel Size

Some entities act as **associative entities**:
- Product Colors
- Product Categories

Each entity focuses on a single concept, which reflects normalized design principles.

---

## 2. Attributes

Attributes describe the properties of each entity and appear inside each box.

Examples:
- Product: product_id, product_name, other data
- Color: color_id, color_code, color_name
- Category: category_id, category_name, parent_category_id
- Apparel Size: size_id, size_code, sort_order

Each attribute depends on the entity’s primary key and stores a single, atomic value.

---

## 3. Relationships

Relationships define how entities are connected.

Key relationships shown in the diagram:
- A product can have multiple colors  
- A product can belong to multiple categories  
- A product can have multiple sizes  

Many-to-many relationships are resolved using associative entities:
- Product ↔ Color → Product Colors
- Product ↔ Category → Product Categories

This approach avoids data duplication and keeps relationships explicit.

---

## 4. Why This Model Works Well

This design demonstrates:
- Clear separation of concerns between entities
- Minimal data redundancy
- Scalable handling of product variations (size, color, category)
- Logical consistency aligned with normalization principles

The result is a clean, flexible structure that can be implemented easily in a relational database.

---

## Summary

- Entities define what data is stored
- Attributes describe each entity
- Relationships connect entities logically
- Associative entities handle many-to-many relationships

This diagram is a practical example of how logical data modeling turns normalization concepts into a real database structure.
