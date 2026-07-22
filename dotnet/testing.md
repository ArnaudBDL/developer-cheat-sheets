# .NET : Testing

## Test

```csharp
public sealed class CalculatorTests
{
    [Fact]
    public void Add_ReturnsSum()
    {
        Assert.Equal(5, Calculator.Add(2, 3));
    }
}
```

## Run

```bash
dotnet test
dotnet test --configuration Release
dotnet test --filter FullyQualifiedName~CalculatorTests
```

Test behavior, boundaries, failures and authorization. Keep tests deterministic, isolate external systems, and separate fast unit tests from integration and end-to-end tests.
