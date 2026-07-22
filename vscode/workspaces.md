# Visual Studio Code : Workspaces

## Workspace Types

```text
Single-folder workspace
Multi-root workspace
Empty window without a workspace
```

## Multi-Root File

```json
{
  "folders": [
    { "path": "frontend" },
    { "path": "backend" }
  ],
  "settings": {
    "files.exclude": {
      "**/.cache": true
    }
  }
}
```

## Workspace Files

```text
.vscode/settings.json
.vscode/tasks.json
.vscode/launch.json
.vscode/extensions.json
project.code-workspace
```

A workspace is one or more folders opened in a VS Code window. It can persist project settings, tasks, debug configurations, extension state and UI state. Commit only settings useful and safe for the team.
