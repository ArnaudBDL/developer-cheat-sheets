# .NET : Dependency Injection

## Registration

```csharp
builder.Services.AddSingleton<IClock, SystemClock>();
builder.Services.AddScoped<IOrderService, OrderService>();
builder.Services.AddTransient<IMessageFormatter, MessageFormatter>();
```

## Lifetimes

```text
Singleton   One instance for the container lifetime
Scoped      One instance per scope
Transient   A new instance for each resolution
```

Do not inject scoped services into singletons. Keep registration centralized, prefer constructor injection, and avoid service-locator access in domain code.
