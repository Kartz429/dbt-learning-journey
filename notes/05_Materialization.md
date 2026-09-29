# Materialization

[← 04 Source vs Ref](04_Source_vs_Ref.md) | [Index](README.md) | [06 Data Tests →](06_Data_Tests.md)

## 1. Concept
Model ka result kaise store ho: view, table, incremental, ephemeral.

## 2. Purpose
Speed vs storage vs freshness ka balance.

## 3. Why It Exists
- ❌ Without: Har model table ban jaye to slow aur mehnga.
- ✅ With: Sahi type chuno.

## 4. Real-World Use Case
Bade fact table incremental, chhote dims table/view.

## 5. SQL Example
```sql
create table gold_sales as select ...;
```

## 6. DBT Example
```sql
{{ config(materialized='table') }}
```

## 7. Hands-On Implementation (from this project)
dbt_project.yml me example/ = view. gold_sales = table, my_first_dbt_model = table, fact_orders_incremental = incremental. Baaki models default (view).

## 8. Commands Used
`dbt run --select gold_sales`

## 9. Common Mistakes
- Bade table ko view rakhna ya chhote ko incremental banana.

## 10. Best Practices
- Default view, bhaari models table/incremental.

## 11. Interview Questions
**Q:** View vs table?
**A:** View query time par chalta hai, table stored hota hai.
**Follow-up:** Ephemeral kab?

## 12. Revision Notes
- View halka, table fast, incremental smart.

## 13. One-Line Summary
Materialization decide karta hai result kaise save hoga.

---
[← 04 Source vs Ref](04_Source_vs_Ref.md) | [Index](README.md) | [06 Data Tests →](06_Data_Tests.md)
