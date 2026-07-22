# .NET : Installation

## Verify

```bash
dotnet --version
dotnet --info
dotnet --list-sdks
dotnet --list-runtimes
```

## First Application

```bash
dotnet new console -n HelloDotNet
cd HelloDotNet
dotnet run
```

Install the .NET SDK for development. The SDK includes the `dotnet` CLI. Pin the supported SDK for the repository where reproducibility matters, and verify the selected SDK before building.
