# .NET : Publishing

## Publish

```bash
dotnet publish -c Release
dotnet publish -c Release -o ./artifacts/publish
dotnet publish -c Release -r linux-x64 --self-contained false
```

## Deployment Models

```text
Framework-dependent
Self-contained
Single-file where supported
Trimmed where compatible and tested
Native AOT where compatible and tested
```

Test the exact published artifact, include runtime and architecture decisions in deployment metadata, and verify reflection, globalization and dynamic-loading behavior before trimming or AOT deployment.
