# .NET : Classes

## Class

```csharp
public sealed class User
{
    public User(Guid id, string displayName)
    {
        Id = id;
        DisplayName = displayName ?? throw new ArgumentNullException(nameof(displayName));
    }

    public Guid Id { get; }
    public string DisplayName { get; private set; }
}
```

Encapsulate state, establish invariants during construction, prefer composition to deep inheritance, and use `sealed` when inheritance is not part of the contract.
