# Jinja

[← 06 Data Tests](06_Data_Tests.md) | [Index](README.md) | [08 Macros →](08_Macros.md)

## 1. Concept
SQL ke andar Python-jaisa templating: {{ }} value, {% %} logic.

## 2. Purpose
SQL me variables, loops, conditions.

## 3. Why It Exists
- ❌ Without: Repeat SQL copy-paste.
- ✅ With: Loop/variable se DRY code.

## 4. Real-World Use Case
Countries ki list se union all banana.

## 5. SQL Example
```sql
select 'India' as country union all select 'USA' ...
```

## 6. DBT Example
```sql
{% set countries = ['India','USA','UK'] %}
{% for c in countries %} '{{ c }}' as country {% if not loop.last %} union all {% endif %}{% endfor %}
```

## 7. Hands-On Implementation (from this project)
models/gold/jinja_demo.sql ({% set %}), loop_demo.sql ({% for %} + loop.last), fact_orders_incremental.sql ({% if is_incremental() %}).

## 8. Commands Used
`dbt compile`

## 9. Common Mistakes
- loop.last bhoolna → SQL syntax error.

## 10. Best Practices
- Jinja limited rakho, readable SQL pehle.

## 11. Interview Questions
**Q:** dbt compile kya karta hai?
**A:** Jinja render karke pure SQL banata hai.
**Follow-up:** is_incremental kaise kaam karta hai?

## 12. Revision Notes
- {{ }} = value, {% %} = logic.

## 13. One-Line Summary
Jinja SQL ko dynamic banata hai.

---
[← 06 Data Tests](06_Data_Tests.md) | [Index](README.md) | [08 Macros →](08_Macros.md)
