# .NET : ASP.NET Core

## Minimal Application

```csharp
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddHealthChecks();

var app = builder.Build();
app.UseHttpsRedirection();
app.MapHealthChecks("/health");
app.Run();
```

## Pipeline

```text
Configuration
Service registration
Middleware
Authentication
Authorization
Endpoint mapping
Error handling
Observability
```

Middleware order affects behavior. Keep secrets out of configuration files, enforce HTTPS and authorization, validate forwarded-header and proxy configuration, and expose only necessary diagnostic endpoints.
