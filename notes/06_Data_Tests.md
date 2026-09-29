# Data Tests

[← 05 Materialization](05_Materialization.md) | [Index](README.md) | [07 Jinja →](07_Jinja.md)

## 1. Concept
Automatic checks jaise unique, not_null jo fail hone par bug pakadte hain.

## 2. Purpose
Bad data dashboard tak pahunchne se pehle rokna.

## 3. Why It Exists
- ❌ Without: Duplicate order_id se GMV galat.
- ✅ With: unique + not_null test turant fail karta hai.

## 4. Real-World Use Case
order_id duplicate na ho.

## 5. SQL Example
```sql
select order_id from fact_orders group by 1 having count(*)>1;
```

## 6. DBT Example
```sql
columns:
  - name: order_id
    tests: [unique, not_null]
```

## 7. Hands-On Implementation (from this project)
models/gold/schema.yml: fact_orders.order_id par unique + not_null. models/example/schema.yml: starter models par unique/not_null (my_first_dbt_model me jaan-boojhkar null id hai, isliye not_null fail hoga). tests/ folder khali hai (singular tests nahi).

## 8. Commands Used
`dbt test, dbt test --select fact_orders`

## 9. Common Mistakes
- Sirf ek model par test lagana; relationships test bhoolna.

## 10. Best Practices
- Har primary key par unique+not_null, foreign key par relationships.

## 11. Interview Questions
**Q:** Generic vs singular test?
**A:** Generic reusable, singular custom SQL file.
**Follow-up:** Test fail par kya hota hai?

## 12. Revision Notes
- Test = data ka watchman.

## 13. One-Line Summary
Tests data quality automatic check karte hain.

---
[← 05 Materialization](05_Materialization.md) | [Index](README.md) | [07 Jinja →](07_Jinja.md)
