# source() vs ref()

[← 03 Medallion Architecture](03_Medallion_Architecture.md) | [Index](README.md) | [05 Materialization →](05_Materialization.md)

## 1. Concept
ref() = dbt model/seed ki taraf point karta hai. source() = dbt ke bahar (warehouse me pehle se loaded) table ki taraf.

## 2. Purpose
Dependency graph banana aur naam environment ke hisaab se badalna.

## 3. Why It Exists
- ❌ Without: Hardcoded table names, dev/prod me toot jaate hain.
- ✅ With: ref()/source() se lineage aur env switching free.

## 4. Real-World Use Case
Ingestion tool ne raw.orders load kiya → source(). Uske upar models → ref().

## 5. SQL Example
```sql
select * from raw.orders
```

## 6. DBT Example
```sql
select * from {{ source('raw','orders') }}   -- ya --   select * from {{ ref('silver_orders') }}
```

## 7. Hands-On Implementation (from this project)
Is project me SIRF ref() use hua hai (bronze models seeds par ref() karte hain). source() aur sources.yml abhi implement nahi hue — ye next step hai.

## 8. Commands Used
`dbt build`

## 9. Common Mistakes
- source() aur ref() mix-up karna; seed par source() lagana.

## 10. Best Practices
- Raw tables ke liye source() + freshness, baaki sab ref().

## 11. Interview Questions
**Q:** Source aur ref me difference?
**A:** Source dbt ke bahar ka raw table, ref dbt-managed object.
**Follow-up:** Source freshness kya hai?

## 12. Revision Notes
- Bahar ka data = source, dbt ka data = ref.

## 13. One-Line Summary
ref() dbt objects ke liye, source() raw external tables ke liye.

---
[← 03 Medallion Architecture](03_Medallion_Architecture.md) | [Index](README.md) | [05 Materialization →](05_Materialization.md)
