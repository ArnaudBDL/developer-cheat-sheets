# Power BI : DAX

## Measure

```dax
Total Sales =
SUM ( Sales[Amount] )
```

## Filter Context

```dax
Sales Previous Year =
CALCULATE (
    [Total Sales],
    SAMEPERIODLASTYEAR ( 'Date'[Date] )
)
```

## Safe Division

```dax
Margin Rate =
DIVIDE ( [Margin], [Total Sales] )
```

## Rules

- Prefer measures for dynamic aggregations.
- Understand row context, filter context and context transition.
- Use variables to improve readability and avoid repeated expressions.
- Reference measures with brackets and qualify column names with table names.
- Use `DIVIDE` when denominator handling matters.
- Test totals separately from row-level results.
- Profile expensive measures with appropriate diagnostic tools.
