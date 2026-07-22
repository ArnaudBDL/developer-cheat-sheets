# .NET : Entity Framework Core

## DbContext

```csharp
public sealed class ApplicationDbContext(DbContextOptions<ApplicationDbContext> options)
    : DbContext(options)
{
    public DbSet<Order> Orders => Set<Order>();
}
```

## Query

```csharp
Order? order = await dbContext.Orders
    .AsNoTracking()
    .SingleOrDefaultAsync(item => item.Id == id, cancellationToken);
```

## Migrations

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

Review generated migrations, avoid unbounded queries, understand tracking, prevent accidental N+1 access, and keep database credentials outside source control.
