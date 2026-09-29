# Roadmap
1. Fix known model issues (see learning_progress.md).
2. Add `sources.yml` and use `source()` for raw tables.
3. Add tests: relationships, accepted_values, singular tests in tests/.
4. Replace row_number() surrogate key with hash-based key.
5. Add layer configs in dbt_project.yml (bronze=view, silver=view, gold=table).
6. Add profiles.yml.example documenting dev/prod targets.
7. Add GitHub Actions: `dbt build` on pull request.
8. Generate dbt docs and add lineage screenshot.
9. Explore packages (dbt_utils), exposures, and model contracts.
