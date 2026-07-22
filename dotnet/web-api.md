# .NET : Web API

## Endpoint

```csharp
app.MapGet("/orders/{id:guid}", async (
    Guid id,
    IOrderRepository repository,
    CancellationToken cancellationToken) =>
{
    Order? order = await repository.FindAsync(id, cancellationToken);
    return order is null ? Results.NotFound() : Results.Ok(order);
});
```

## API Controls

```text
Input validation
Authentication and authorization
Problem details
Pagination
Idempotency
Rate limits
OpenAPI contract
Versioning policy
```

Return appropriate HTTP semantics, avoid leaking internal models directly, and authorize both the operation and target resource.
