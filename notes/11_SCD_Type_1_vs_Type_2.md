# SCD Type 1 vs Type 2

[← 10 Snapshots](10_Snapshots.md) | [Index](README.md) | [12 Incremental Models →](12_Incremental_Models.md)

## 1. Concept
SCD = Slowly Changing Dimension. Type 1 = overwrite, Type 2 = history rakho.

## 2. Purpose
Dimension change ko sahi handle karna.

## 3. Why It Exists
- ❌ Without: Type 1 me history gayab.
- ✅ With: Type 2 me history safe.

## 4. Real-World Use Case
Customer city change.

## 5. SQL Example
```sql
update customers set city='Pune' where customer_id=1;
```

## 6. DBT Example
```sql
scd_type1_demo (overwrite) vs customers_snapshot + dim_customers_scd2 (Type 2)
```

## 7. Hands-On Implementation (from this project)
scd_type1_demo.sql aur scd_type2_demo.sql hardcoded demo rows hain. Asli Type 2 = customers_snapshot + dim_customers_scd2.

## 8. Commands Used
`dbt snapshot`

## 9. Common Mistakes
- Type 2 me current row filter na karna.

## 10. Best Practices
- History chahiye to Type 2.

## 11. Interview Questions
**Q:** Type 1 vs 2?
**A:** Overwrite vs history.
**Follow-up:** Type 3 kya hai?

## 12. Revision Notes
- Type 1 overwrite, Type 2 history.

## 13. One-Line Summary
SCD2 history ke saath naya row banata hai.

---
[← 10 Snapshots](10_Snapshots.md) | [Index](README.md) | [12 Incremental Models →](12_Incremental_Models.md)
