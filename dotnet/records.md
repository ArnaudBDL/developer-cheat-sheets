# .NET : Records

## Record

```csharp
public sealed record Product(
    string Id,
    string Name,
    decimal Price);
```

## Non-Destructive Mutation

```csharp
Product discounted = product with { Price = product.Price * 0.9m };
```

Records provide value-oriented equality and concise data declarations. Referenced members can still be mutable, so use immutable component types where stable value semantics matter.
