# CI/CD

[← 18 Environment Management](18_Environment_Management.md) | [Index](README.md) | [20 Project Summary →](20_Project_Summary.md)

## 1. Concept
CI = har push par auto tests, CD = auto deploy.

## 2. Purpose
Bug prod tak na pahunche.

## 3. Why It Exists
- ❌ Without: Manual checks.
- ✅ With: Auto validation.

## 4. Real-World Use Case
PR par dbt build.

## 5. SQL Example
```sql
-- N/A
```

## 6. DBT Example
```sql
GitHub Actions: dbt build --select state:modified+
```

## 7. Hands-On Implementation (from this project)
STATUS: abhi implement nahi hua — project me .github/workflows nahi hai. Ye sirf concept note hai; automation/ folder sirf git sync karta hai, CI nahi.

## 8. Commands Used
`dbt build`

## 9. Common Mistakes
- CI ko sirf lint samajhna.

## 10. Best Practices
- Slim CI.

## 11. Interview Questions
**Q:** Slim CI?
**A:** Sirf changed models test.
**Follow-up:** State comparison?

## 12. Revision Notes
- CI = auto check.

## 13. One-Line Summary
CI/CD automatic validation aur deployment hai.

---
[← 18 Environment Management](18_Environment_Management.md) | [Index](README.md) | [20 Project Summary →](20_Project_Summary.md)
