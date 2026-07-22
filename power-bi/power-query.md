# Power BI : Power Query

## Transformation Flow

```text
Connect
Select required columns and rows
Correct data types
Clean and normalize values
Merge or append queries
Create reusable staging queries
Validate errors and nulls
Load only required outputs
```

## M Example

```powerquery
let
    Source = Csv.Document(File.Contents(ParameterFilePath), [Delimiter=",", Encoding=65001]),
    Headers = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    Typed = Table.TransformColumnTypes(Headers, {{"OrderId", type text}, {"Amount", Currency.Type}})
in
    Typed
```

## Rules

- Filter early and load only required columns.
- Preserve query folding when the connector supports it.
- Use parameters for environment-specific paths and servers.
- Disable load for staging queries.
- Name steps and queries clearly.
- Avoid exposing secrets in M code.
- Test refresh outside the authoring machine.
