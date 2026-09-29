# Project Structure

[← 01 DBT Basics](01_DBT_Basics.md) | [Index](README.md) | [03 Medallion Architecture →](03_Medallion_Architecture.md)

## 1. Concept
dbt project ek fixed folder layout follow karta hai jo dbt_project.yml se define hota hai.

## 2. Purpose
Code ko organize rakhna taaki dbt sab kuch khud dhoondh le.

## 3. Why It Exists
- ❌ Without: Sab files ek folder me, kuch pata nahi kya model hai kya seed.
- ✅ With: models/, seeds/, snapshots/, macros/, tests/, analyses/ alag alag.

## 4. Real-World Use Case
Team me naya banda folder dekhkar samajh jaye.

## 5. SQL Example
```sql
-- N/A
```

## 6. DBT Example
```sql
model-paths: ["models"]  seed-paths: ["seeds"]  snapshot-paths: ["snapshots"]  macro-paths: ["macros"]
```

## 7. Hands-On Implementation (from this project)
Is project me: models/{bronze,silver,gold,example}, seeds/ (4 CSV), snapshots/customers_snapshot.sql, macros/customer_type.sql, automation/ (Python sync scripts). tests/ aur analyses/ abhi khali hain (.gitkeep).

## 8. Commands Used
`dbt ls, dbt clean`

## 9. Common Mistakes
- Starter `example/` folder aur demo models ko production folder me chhod dena.

## 10. Best Practices
- Layer-wise folders (bronze/silver/gold) aur `+materialized` dbt_project.yml me set karo.

## 11. Interview Questions
**Q:** dbt_project.yml ka role?
**A:** Project ka naam, profile, paths aur default configs define karta hai.
**Follow-up:** profiles.yml alag kyu hoti hai?

## 12. Revision Notes
- Folder = kaam ka label.

## 13. One-Line Summary
Folder layout dbt ko batata hai kaunsi file kya hai.

---
[← 01 DBT Basics](01_DBT_Basics.md) | [Index](README.md) | [03 Medallion Architecture →](03_Medallion_Architecture.md)
