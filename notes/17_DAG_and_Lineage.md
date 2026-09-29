# DAG and Lineage

[← 16 Surrogate Keys](16_Surrogate_Keys.md) | [Index](README.md) | [18 Environment Management →](18_Environment_Management.md)

## 1. Concept
DAG = Directed Acyclic Graph, models ka dependency map.

## 2. Purpose
Sahi order me run.

## 3. Why It Exists
- ❌ Without: Order manual.
- ✅ With: ref() se auto.

## 4. Real-World Use Case
Impact analysis.

## 5. SQL Example
```sql
-- N/A
```

## 6. DBT Example
```sql
dbt docs generate && dbt docs serve
```

## 7. Hands-On Implementation (from this project)
seeds → bronze → silver → (snapshot → dim_customers_scd2, dim_restaurants) → fact_orders → mart_gmv. Details project repo ke dag_explanation.md me.

## 8. Commands Used
`dbt docs generate, dbt ls --select +mart_gmv`

## 9. Common Mistakes
- Circular dependency.

## 10. Best Practices
- Lineage screenshot README me.

## 11. Interview Questions
**Q:** DAG acyclic kyu?
**A:** Loop se infinite dependency.
**Follow-up:** +model kya?

## 12. Revision Notes
- ref() = arrow.

## 13. One-Line Summary
DAG dependencies dikhata hai.

---
[← 16 Surrogate Keys](16_Surrogate_Keys.md) | [Index](README.md) | [18 Environment Management →](18_Environment_Management.md)
