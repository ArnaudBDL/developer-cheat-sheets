# .NET : Quick References

## CLI

```bash
dotnet --info
dotnet new console -n Application
dotnet restore
dotnet build
dotnet test
dotnet run
dotnet publish -c Release
```

## Packages

```bash
dotnet add package Package.Name
dotnet list package
dotnet list package --outdated
```

## Diagnostics

```bash
dotnet-counters monitor --process-id <pid>
dotnet-trace collect --process-id <pid>
dotnet-dump collect --process-id <pid>
```
