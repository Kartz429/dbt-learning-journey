# Seeds

[← 08 Macros](08_Macros.md) | [Index](README.md) | [10 Snapshots →](10_Snapshots.md)

## 1. Concept
Seeds = CSV files jo dbt table ki tarah load karta hai.

## 2. Purpose
Chhota static data version control me rakhna.

## 3. Why It Exists
- ❌ Without: Lookup data manual upload.
- ✅ With: dbt seed se ek command me load.

## 4. Real-World Use Case
Country codes, demo data.

## 5. SQL Example
```sql
insert into customers values (1,'Kartik','Mumbai');
```

## 6. DBT Example
```sql
dbt seed  →  {{ ref('customers') }}
```

## 7. Hands-On Implementation (from this project)
seeds/: customers.csv (4 rows), orders.csv (5), restaurants.csv (3), country_codes.csv (3). Yahan seeds bronze ka raw input hain.

## 8. Commands Used
`dbt seed`

## 9. Common Mistakes
- Bade data ko seed banana.

## 10. Best Practices
- Sirf chhota/static data seed me.

## 11. Interview Questions
**Q:** Seed kab use nahi karte?
**A:** Large ya frequently changing data.
**Follow-up:** Seed ko ref kaise karte hain?

## 12. Revision Notes
- Seed = CSV as table.

## 13. One-Line Summary
Seeds chhote CSV data ko dbt me load karte hain.

---
[← 08 Macros](08_Macros.md) | [Index](README.md) | [10 Snapshots →](10_Snapshots.md)
