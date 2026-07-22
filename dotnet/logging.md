# .NET : Logging

## Structured Logging

```csharp
public sealed class Worker(ILogger<Worker> logger)
{
    public void Process(Guid orderId)
    {
        logger.LogInformation("Processing order {OrderId}", orderId);
    }
}
```

Use message templates rather than string interpolation for structured fields. Select levels consistently, preserve correlation identifiers, and never log passwords, tokens, private keys or unnecessary personal data.
