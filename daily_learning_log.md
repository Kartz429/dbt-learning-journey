# Daily Learning Log

## 2026-09-29
- Reviewed full project: 3 bronze, 3 silver, gold dims/facts/marts, 1 snapshot, 1 macro, 4 seeds.
- Identified SCD2 flow: silver_customers → customers_snapshot → dim_customers_scd2.
- Found model issues by code reading (not run): gold_sales, macro_demo, mart_city_sales reference columns that don't exist upstream.
- Learned: fact join to SCD2 dim needs a validity-window condition.
- Automation note: sync scripts overwrite README.md on every run.

## 2026-09-29 (repository cleanup)
- Reorganised notes into `notes/` with one template and prev/next navigation.
- Added `examples/` with real code from the project.
- Archived earlier root-level notes under `archive/original_notes/`.
- Removed README claims for features not implemented yet (CI/CD).
