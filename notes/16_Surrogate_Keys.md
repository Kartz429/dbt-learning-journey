# Surrogate Keys

[← 15 Star Schema](15_Star_Schema.md) | [Index](README.md) | [17 DAG and Lineage →](17_DAG_and_Lineage.md)

## 1. Concept
Surrogate key = system generated unique key.

## 2. Purpose
SCD2 me ek customer ke kai rows unique pehchaan.

## 3. Why It Exists
- ❌ Without: customer_id repeat hota hai history me.
- ✅ With: customer_sk unique.

## 4. Real-World Use Case
SCD2 dim.

## 5. SQL Example
```sql
row_number() over(...)
```

## 6. DBT Example
```sql
row_number() over(order by customer_id, dbt_valid_from) as customer_sk
```

## 7. Hands-On Implementation (from this project)
dim_customers_scd2.sql. Note: row_number() keys run ke saath badal sakte hain; hash-based key (customer_id + dbt_valid_from) stable hota hai.

## 8. Commands Used
`dbt run --select dim_customers_scd2`

## 9. Common Mistakes
- Unstable keys.

## 10. Best Practices
- Deterministic hash key.

## 11. Interview Questions
**Q:** Natural vs surrogate?
**A:** Business key vs generated.
**Follow-up:** Stable key kaise?

## 12. Revision Notes
- SK = stable unique id.

## 13. One-Line Summary
Surrogate key dimension row ko unique pehchaan deti hai.

---
[← 15 Star Schema](15_Star_Schema.md) | [Index](README.md) | [17 DAG and Lineage →](17_DAG_and_Lineage.md)
