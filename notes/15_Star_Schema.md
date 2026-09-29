# Star Schema

[← 14 Fact Tables](14_Fact_Tables.md) | [Index](README.md) | [16 Surrogate Keys →](16_Surrogate_Keys.md)

## 1. Concept
Beech me fact, charon taraf dimensions.

## 2. Purpose
Simple, fast BI queries.

## 3. Why It Exists
- ❌ Without: Complex joins.
- ✅ With: Simple joins.

## 4. Real-World Use Case
GMV by city.

## 5. SQL Example
```sql
select city, sum(amount) from fact join dim ...
```

## 6. DBT Example
```sql
fact_orders → dim_customers_scd2, dim_restaurants
```

## 7. Hands-On Implementation (from this project)
Star: fact_orders center, dim_customers_scd2 + dim_restaurants around. mart_gmv is star par bana hai.

## 8. Commands Used
`dbt docs generate`

## 9. Common Mistakes
- Snowflake schema me over-normalize.

## 10. Best Practices
- Star ko default rakho.

## 11. Interview Questions
**Q:** Star vs Snowflake?
**A:** Denormalized vs normalized dims.
**Follow-up:** Kab snowflake?

## 12. Revision Notes
- Star = fact + dims.

## 13. One-Line Summary
Star schema BI ke liye simple modeling hai.

---
[← 14 Fact Tables](14_Fact_Tables.md) | [Index](README.md) | [16 Surrogate Keys →](16_Surrogate_Keys.md)
