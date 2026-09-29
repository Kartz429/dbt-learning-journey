# Dimension Tables

[← 12 Incremental Models](12_Incremental_Models.md) | [Index](README.md) | [14 Fact Tables →](14_Fact_Tables.md)

## 1. Concept
Dimension = describing data (who/what/where).

## 2. Purpose
Filters aur grouping ke liye context.

## 3. Why It Exists
- ❌ Without: Facts me text repeat.
- ✅ With: Alag dim table.

## 4. Real-World Use Case
Customer, restaurant.

## 5. SQL Example
```sql
select * from dim_customers;
```

## 6. DBT Example
```sql
select * from {{ ref('silver_customers') }}
```

## 7. Hands-On Implementation (from this project)
dim_customers, dim_restaurants (silver se select *), dim_customers_scd2 (snapshot based).

## 8. Commands Used
`dbt run --select dim_customers dim_restaurants`

## 9. Common Mistakes
- Dimension me metrics daalna.

## 10. Best Practices
- Descriptive attributes + key.

## 11. Interview Questions
**Q:** Dimension kya?
**A:** Descriptive table.
**Follow-up:** Conformed dimension?

## 12. Revision Notes
- Dimension = context.

## 13. One-Line Summary
Dimension tables descriptive attributes rakhte hain.

---
[← 12 Incremental Models](12_Incremental_Models.md) | [Index](README.md) | [14 Fact Tables →](14_Fact_Tables.md)
