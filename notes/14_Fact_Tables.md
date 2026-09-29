# Fact Tables

[← 13 Dimension Tables](13_Dimension_Tables.md) | [Index](README.md) | [15 Star Schema →](15_Star_Schema.md)

## 1. Concept
Fact = measurable events (amount, order).

## 2. Purpose
Numbers aggregate karna.

## 3. Why It Exists
- ❌ Without: Numbers alag alag jagah.
- ✅ With: Ek central fact.

## 4. Real-World Use Case
Orders.

## 5. SQL Example
```sql
select sum(amount) from fact_orders;
```

## 6. DBT Example
```sql
fact_orders joins silver_orders with dims
```

## 7. Hands-On Implementation (from this project)
fact_orders.sql: order_id, customer_sk, restaurant_sk(=restaurant_id, real surrogate nahi), amount, status. Known issue: customer join validity window ke bina hota hai → history hone par duplicate rows.

## 8. Commands Used
`dbt run --select fact_orders`

## 9. Common Mistakes
- Grain define na karna; join fan-out.

## 10. Best Practices
- Grain document karo, FK test lagao.

## 11. Interview Questions
**Q:** Fact grain?
**A:** Ek row = ek order.
**Follow-up:** Fan-out kaise pakadte?

## 12. Revision Notes
- Fact = numbers, dim = context.

## 13. One-Line Summary
Fact tables business events aur measures rakhte hain.

---
[← 13 Dimension Tables](13_Dimension_Tables.md) | [Index](README.md) | [15 Star Schema →](15_Star_Schema.md)
