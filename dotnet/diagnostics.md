# .NET : Diagnostics

## Environment

```bash
dotnet --info
dotnet --list-sdks
dotnet --list-runtimes
```

## Runtime Tools

```bash
dotnet-counters ps
dotnet-counters monitor --process-id <pid>
dotnet-trace collect --process-id <pid>
dotnet-dump collect --process-id <pid>
```

Collect diagnostics only under approved procedures. Dumps and traces can contain credentials, personal data and application payloads, so protect access, storage and retention.
