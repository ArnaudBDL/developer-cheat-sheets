# .NET : Configuration

## Configuration Sources

```text
appsettings.json
appsettings.Environment.json
Environment variables
Command-line arguments
Approved external configuration providers
```

## Options

```csharp
builder.Services.Configure<StorageOptions>(
    builder.Configuration.GetSection("Storage"));
```

## Environment Variable

```bash
export Storage__Endpoint="https://example.invalid"
```

Later providers can override earlier values. Validate configuration at startup, use strongly typed options, and keep production secrets in an approved secret store rather than JSON files.
