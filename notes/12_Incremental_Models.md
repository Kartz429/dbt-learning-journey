# Incremental Models

[← 11 SCD Type 1 vs Type 2](11_SCD_Type_1_vs_Type_2.md) | [Index](README.md) | [13 Dimension Tables →](13_Dimension_Tables.md)

## 1. Concept
Sirf naya data process karo, poora table nahi.

## 2. Purpose
Time aur cost bachana.

## 3. Why It Exists
- ❌ Without: Har run me poora reload.
- ✅ With: Sirf new rows.

## 4. Real-World Use Case
Daily lakhon orders.

## 5. SQL Example
```sql
insert into t select * from src where id > (select max(id) from t);
```

## 6. DBT Example
```sql
{{ config(materialized='incremental', unique_key='order_id') }} ... {% if is_incremental() %} where order_id > (select max(order_id) from {{ this }}) {% endif %}
```

## 7. Hands-On Implementation (from this project)
gold/fact_orders_incremental.sql (unique_key=order_id, filter order_id > max). Limitation: late/updated rows miss ho sakte hain; timestamp based filter better.

## 8. Commands Used
`dbt run --select fact_orders_incremental, dbt run --full-refresh`

## 9. Common Mistakes
- is_incremental block bhoolna; unique_key na dena.

## 10. Best Practices
- Timestamp watermark + full-refresh plan.

## 11. Interview Questions
**Q:** is_incremental kab true?
**A:** Table exist ho aur full-refresh na ho.
**Follow-up:** Late arriving data?

## 12. Revision Notes
- Incremental = sirf naya.

## 13. One-Line Summary
Incremental models sirf naya data process karte hain.

---
[← 11 SCD Type 1 vs Type 2](11_SCD_Type_1_vs_Type_2.md) | [Index](README.md) | [13 Dimension Tables →](13_Dimension_Tables.md)
