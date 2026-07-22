# .NET : Async and Await

## Asynchronous Method

```csharp
public async Task<string> DownloadAsync(
    Uri uri,
    CancellationToken cancellationToken)
{
    return await httpClient.GetStringAsync(uri, cancellationToken);
}
```

## Parallel Await

```csharp
string[] results = await Task.WhenAll(tasks);
```

Propagate cancellation, avoid blocking with `.Result` or `.Wait()`, bound concurrency, and do not use `async void` except for required event-handler signatures.
