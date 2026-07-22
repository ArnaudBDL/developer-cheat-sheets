# .NET : Exceptions

## Handling

```csharp
try
{
    return parser.Parse(input);
}
catch (FormatException exception)
{
    throw new ConfigurationException("Invalid configuration.", exception);
}
```

## Dispose

```csharp
await using var stream = File.OpenRead(path);
```

Catch only exceptions you can handle or translate meaningfully. Preserve causes, use `using` or `await using` for disposable resources, and avoid exposing stack traces or secrets to clients.
