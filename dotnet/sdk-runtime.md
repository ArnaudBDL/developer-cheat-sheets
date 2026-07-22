# .NET : SDK and Runtime

## Responsibilities

```text
SDK      Creates, restores, builds, tests and publishes applications.
Runtime  Executes applications targeting a compatible framework.
Host     Selects and starts the appropriate runtime.
```

## Inspect

```bash
dotnet --list-sdks
dotnet --list-runtimes
dotnet --info
```

## global.json

```json
{
  "sdk": {
    "version": "10.0.100",
    "rollForward": "latestPatch"
  }
}
```

The installed SDK and the project target framework are distinct choices. Keep local, CI and production compatibility explicit.
