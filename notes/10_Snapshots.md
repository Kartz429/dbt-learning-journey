# Snapshots

[← 09 Seeds](09_Seeds.md) | [Index](README.md) | [11 SCD Type 1 vs Type 2 →](11_SCD_Type_1_vs_Type_2.md)

## 1. Concept
Snapshot table ki history capture karta hai (kab kya badla).

## 2. Purpose
Purani values kho na jayein.

## 3. Why It Exists
- ❌ Without: City badli to purani city gayab.
- ✅ With: Har change ka naya row + validity dates.

## 4. Real-World Use Case
Customer Mumbai se Pune gaya, purane orders Mumbai me count ho.

## 5. SQL Example
```sql
-- manual: update + insert history row
```

## 6. DBT Example
```sql
{% snapshot customers_snapshot %}{{ config(unique_key='customer_id', strategy='check', check_cols=['city']) }} select * from {{ ref('silver_customers') }}{% endsnapshot %}
```

## 7. Hands-On Implementation (from this project)
snapshots/customers_snapshot.sql: check strategy, city column track. Output dbt_valid_from/dbt_valid_to dim_customers_scd2 me use hote hain.

## 8. Commands Used
`dbt snapshot`

## 9. Common Mistakes
- Snapshot run karna bhool jana; wrong check_cols.

## 10. Best Practices
- Regular schedule par run karo.

## 11. Interview Questions
**Q:** check vs timestamp strategy?
**A:** check columns compare, timestamp updated_at par.
**Follow-up:** Hard delete kaise handle?

## 12. Revision Notes
- Snapshot = time machine.

## 13. One-Line Summary
Snapshot row-level history banata hai.

---
[← 09 Seeds](09_Seeds.md) | [Index](README.md) | [11 SCD Type 1 vs Type 2 →](11_SCD_Type_1_vs_Type_2.md)
