# Macros

[← 07 Jinja](07_Jinja.md) | [Index](README.md) | [09 Seeds →](09_Seeds.md)

## 1. Concept
Macro = reusable SQL/Jinja function.

## 2. Purpose
Ek logic ek jagah, kai jagah use.

## 3. Why It Exists
- ❌ Without: Har model me same CASE copy-paste.
- ✅ With: Ek macro, change ek jagah.

## 4. Real-World Use Case
VIP/NORMAL customer classification.

## 5. SQL Example
```sql
case when amount > 200 then 'VIP' else 'NORMAL' end
```

## 6. DBT Example
```sql
{% macro customer_type(amount_column) %} case when {{ amount_column }} > 200 then 'VIP' else 'NORMAL' end {% endmacro %}
```

## 7. Hands-On Implementation (from this project)
macros/customer_type.sql; macro_demo.sql me call hua. NOTE: macro_demo silver_orders se customer_name select karta hai jo us model me hai hi nahi — run par fail hoga (code padhkar dekha, run nahi kiya).

## 8. Commands Used
`dbt run --select macro_demo`

## 9. Common Mistakes
- Macro me hardcoded threshold; column exist na karna.

## 10. Best Practices
- Threshold ko var/argument banao.

## 11. Interview Questions
**Q:** Macro kab banaye?
**A:** Jab logic 2+ jagah repeat ho.
**Follow-up:** Macro vs CTE?

## 12. Revision Notes
- Macro = SQL ka function.

## 13. One-Line Summary
Macros repeat logic ko reusable banate hain.

---
[← 07 Jinja](07_Jinja.md) | [Index](README.md) | [09 Seeds →](09_Seeds.md)
