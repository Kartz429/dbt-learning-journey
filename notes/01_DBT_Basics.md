# DBT Basics

[Index](README.md) | [02 Project Structure →](02_Project_Structure.md)

## 1. Concept
DBT = Data Build Tool. Ye warehouse ke andar SQL SELECT likhne par table/view bana deta hai. Sirf 'T' (Transform) karta hai, Extract/Load nahi.

## 2. Purpose
Raw data ko analytics-ready data me badalna, version control + testing ke saath.

## 3. Why It Exists
- ❌ Without: Alag-alag SQL scripts, koi order nahi, koi test nahi, kaun kispe depend karta hai pata nahi.
- ✅ With: Har SQL ek model, dependency ref() se, tests aur docs ek jagah.

## 4. Real-World Use Case
Food delivery company me raw orders ko clean karke GMV dashboard ke liye ready karna.

## 5. SQL Example
```sql
select order_id, amount from raw.orders where status = 'delivered';
```

## 6. DBT Example
```sql
select order_id, amount from {{ ref('silver_orders') }} where status = 'delivered'
```

## 7. Hands-On Implementation (from this project)
Project `my_first_project` (dbt_project.yml) — seeds → bronze → silver → gold, DuckDB par (dev.duckdb / prod.duckdb files project me hain).

## 8. Commands Used
`dbt debug, dbt run, dbt test, dbt build`

## 9. Common Mistakes
- 'dbt data load karta hai' bolna galat hai. Sirf transform karta hai.

## 10. Best Practices
- Har model chhota aur ek kaam ka rakho.

## 11. Interview Questions
**Q:** dbt ELT me kahan fit hota hai?
**A:** Load ke baad warehouse ke andar Transform karta hai.
**Follow-up:** dbt aur Airflow me kya farak?

## 12. Revision Notes
- dbt = SQL + ref() + tests + docs.

## 13. One-Line Summary
dbt warehouse ke andar SQL ko tables/views me badalne wala transformation tool hai.

---
[Index](README.md) | [02 Project Structure →](02_Project_Structure.md)
