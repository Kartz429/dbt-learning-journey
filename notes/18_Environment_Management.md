# Environment Management (Dev vs Prod)

[← 17 DAG and Lineage](17_DAG_and_Lineage.md) | [Index](README.md) | [19 CI CD →](19_CI_CD.md)

## 1. Concept
Alag targets: dev (test) aur prod (real).

## 2. Purpose
Prod safe.

## 3. Why It Exists
- ❌ Without: Direct prod me test.
- ✅ With: Dev me test, prod me release.

## 4. Real-World Use Case
Naya model dev me.

## 5. SQL Example
```sql
-- N/A
```

## 6. DBT Example
```sql
dbt run --target dev / --target prod
```

## 7. Hands-On Implementation (from this project)
Project me dev.duckdb aur prod.duckdb files hain, par profiles.yml zip me nahi, isliye target config verify nahi hua. Bas itna confirmed.

## 8. Commands Used
`dbt run --target prod`

## 9. Common Mistakes
- Prod par direct run.

## 10. Best Practices
- Alag schema/db.

## 11. Interview Questions
**Q:** Target kya?
**A:** profiles.yml ka environment.
**Follow-up:** Dev/prod schema separation?

## 12. Revision Notes
- Dev test, prod real.

## 13. One-Line Summary
Environments dev aur prod ko alag rakhte hain.

---
[← 17 DAG and Lineage](17_DAG_and_Lineage.md) | [Index](README.md) | [19 CI CD →](19_CI_CD.md)
