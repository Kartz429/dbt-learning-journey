# Medallion Architecture (Bronze-Silver-Gold)

[← 02 Project Structure](02_Project_Structure.md) | [Index](README.md) | [04 Source vs Ref →](04_Source_vs_Ref.md)

## 1. Concept
Data ko 3 layers me clean karte jao: Bronze (raw), Silver (cleaned), Gold (business-ready).

## 2. Purpose
Har layer ka ek clear kaam, debugging aasan.

## 3. Why It Exists
- ❌ Without: Ek hi query me raw se dashboard tak, toota to pata nahi kahan.
- ✅ With: Har layer alag model; bug layer se pakad lo.

## 4. Real-World Use Case
Bronze me raw orders, Silver me status lowercase, Gold me GMV mart.

## 5. SQL Example
```sql
select lower(status) as status from bronze_orders;
```

## 6. DBT Example
```sql
select order_id, lower(status) as status from {{ ref('bronze_orders') }}
```

## 7. Hands-On Implementation (from this project)
Bronze: bronze_customers/orders/restaurants (select * from ref(seed)). Silver: upper(customer_name), upper(restaurant_name), lower(status). Gold: dim_*, fact_orders, mart_gmv.

## 8. Commands Used
`dbt run --select bronze silver gold (path selectors)`

## 9. Common Mistakes
- Bronze me hi cleaning kar dena.

## 10. Best Practices
- Bronze me raw as-is rakho, Silver me cleaning, Gold me business logic.

## 11. Interview Questions
**Q:** Silver me kya hota hai?
**A:** Cleaning: rename, casing, dedupe, type fix.
**Follow-up:** Bronze skip kar sakte hain kya?

## 12. Revision Notes
- Bronze raw, Silver clean, Gold business.

## 13. One-Line Summary
Medallion = raw → clean → business-ready, 3 steps.

---
[← 02 Project Structure](02_Project_Structure.md) | [Index](README.md) | [04 Source vs Ref →](04_Source_vs_Ref.md)
