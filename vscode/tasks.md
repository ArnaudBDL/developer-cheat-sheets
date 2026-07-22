# Visual Studio Code : Tasks

## tasks.json

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build",
      "type": "shell",
      "command": "npm run build",
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": []
    }
  ]
}
```

## Compound Task

```json
{
  "label": "verify",
  "dependsOn": ["lint", "test"],
  "dependsOrder": "sequence"
}
```

Run tasks from **Terminal > Run Task** or the Command Palette. Commit safe project tasks, avoid embedded secrets, define problem matchers where appropriate, and distinguish build tasks from background watchers.
