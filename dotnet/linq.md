# .NET : LINQ

## Query

```csharp
var activeNames = users
    .Where(user => user.IsActive)
    .OrderBy(user => user.DisplayName)
    .Select(user => user.DisplayName)
    .ToList();
```

## Deferred Execution

```csharp
IEnumerable<Order> openOrders = orders.Where(order => order.IsOpen);
```

LINQ queries can execute lazily. Materialize deliberately, avoid repeated enumeration of expensive sources, and understand whether the provider executes in memory or translates the expression to another system.
