# .NET : Interfaces

## Contract

```csharp
public interface IMessageSender
{
    Task SendAsync(Message message, CancellationToken cancellationToken);
}
```

## Implementation

```csharp
public sealed class EmailSender : IMessageSender
{
    public Task SendAsync(Message message, CancellationToken cancellationToken)
    {
        return Task.CompletedTask;
    }
}
```

Keep interfaces cohesive and behavior-focused. Do not create interfaces only to mirror every class, and avoid leaking implementation-specific types through public contracts.
