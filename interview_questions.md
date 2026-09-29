# Interview Questions (based on this project)

## Beginner
**Q: What is dbt?** A: SQL-based transformation tool that runs inside the warehouse. **Follow-up:** Does dbt load data?
**Q: ref() vs source()?** A: ref for dbt objects, source for raw external tables (this project uses ref only). **Follow-up:** What is source freshness?
**Q: What are seeds?** A: CSVs loaded as tables. **Follow-up:** When not to use them?

## Intermediate
**Q: Explain your Bronze/Silver/Gold layers.** A: Bronze = select * from seeds, Silver = casing/column cleanup, Gold = dims, facts, marts. **Follow-up:** Where would you dedupe?
**Q: Snapshot strategies?** A: check (used, on city) vs timestamp. **Follow-up:** How do you handle hard deletes?
**Q: How does your incremental model work?** A: unique_key=order_id, filters order_id > max. **Follow-up:** What breaks with late data?

## Advanced
**Q: What's wrong with joining a fact to an SCD2 dim on business key?** A: Duplicates rows per version; join on validity window. **Follow-up:** How to test grain?
**Q: Why is row_number() a weak surrogate key?** A: Changes between runs; use hash. **Follow-up:** dbt_utils.generate_surrogate_key?
**Q: How would you add CI?** A: GitHub Actions running dbt build on PR, slim CI with state:modified+. **Follow-up:** Handling secrets?
