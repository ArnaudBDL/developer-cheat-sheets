# .NET : Files and Streams

## Async File Access

```csharp
string content = await File.ReadAllTextAsync(path, cancellationToken);
await File.WriteAllTextAsync(path, updated, cancellationToken);
```

## Stream

```csharp
await using FileStream stream = File.OpenRead(path);
```

Validate and normalize paths, use explicit encodings, bound file sizes, dispose streams, create safe temporary files, and never trust an uploaded filename as a server path.
