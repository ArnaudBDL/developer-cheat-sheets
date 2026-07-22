# .NET : Generics

## Generic Type

```csharp
public sealed class Result<T>
{
    public required T Value { get; init; }
    public bool IsSuccess { get; init; }
}
```

## Constraint

```csharp
public static T Create<T>() where T : new()
{
    return new T();
}
```

Use generics for compile-time reuse and type safety. Keep constraints meaningful, preserve variance rules on interfaces and delegates, and avoid unnecessary reflection-based generic construction.
