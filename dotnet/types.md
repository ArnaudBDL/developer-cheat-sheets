# .NET : Types

## Value and Reference Types

```csharp
bool active = true;
int count = 42;
decimal amount = 19.99m;
DateTimeOffset timestamp = DateTimeOffset.UtcNow;
string name = "Arnaud";
string? optional = null;
```

## Nullable Value

```csharp
int? optionalCount = null;
int resolved = optionalCount ?? 0;
```

Use `decimal` for monetary arithmetic where decimal semantics are required. Distinguish absent values from defaults and enable nullable reference type analysis.
