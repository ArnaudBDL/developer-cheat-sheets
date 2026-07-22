# .NET : Collections

## Core Collections

```csharp
var names = new List<string>();
var tags = new HashSet<string>();
var users = new Dictionary<Guid, User>();
var queue = new Queue<Job>();
var stack = new Stack<Operation>();
```

## Read-Only Exposure

```csharp
public IReadOnlyList<Order> Orders => _orders;
```

Choose collections by ordering, uniqueness, lookup and concurrency needs. Avoid exposing mutable internal collections directly and do not modify ordinary collections while enumerating them.
