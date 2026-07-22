# .NET : Troubleshooting

## Baseline

```bash
dotnet --info
dotnet restore
dotnet build --configuration Debug
dotnet test
```

## NuGet and Build

```bash
dotnet nuget locals all --list
dotnet list package
dotnet build -v:diagnostic
```

## Common Causes

```text
Wrong SDK selected
Missing runtime
Target-framework incompatibility
Unavailable or unauthorized package source
Conflicting transitive packages
Incorrect environment configuration
Port already in use
Certificate trust failure
Database migration mismatch
Sync-over-async deadlock or blocked work
```

Capture the exact command, `dotnet --info`, project target framework, complete error and minimal reproducer. Remove secrets and sensitive paths before sharing diagnostics.
