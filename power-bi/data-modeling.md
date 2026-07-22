# Power BI : Data Modeling

## Star Schema

```text
Dimension tables describe business entities.
Fact tables store events, measurements and foreign keys.
Relationships connect dimensions to facts.
Measures aggregate fact data in filter context.
```

## Relationship Checks

```text
Cardinality
Active or inactive state
Cross-filter direction
Referential integrity
Ambiguous filter paths
Date-table role
```

## Rules

- Prefer clear star schemas over one wide denormalized reporting table.
- Use one-to-many relationships from dimensions to facts.
- Avoid bidirectional filtering unless its behavior is required and tested.
- Hide technical keys and implementation columns from report authors.
- Create a dedicated date table for time analysis.
- Separate reusable semantic models from presentation reports when appropriate.
- Keep naming, display folders and descriptions consistent.
