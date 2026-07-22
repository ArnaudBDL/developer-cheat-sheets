# .NET : Serialization

## System.Text.Json

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase,
    WriteIndented = true
};

string json = JsonSerializer.Serialize(value, options);
Result? result = JsonSerializer.Deserialize<Result>(json, options);
```

Use explicit contracts for public messages, validate deserialized input, set payload limits, avoid unsafe polymorphic handling, and do not deserialize untrusted binary object graphs.
