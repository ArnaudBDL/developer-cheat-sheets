# Visual Studio Code : Debugging

## launch.json

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Launch Program",
      "program": "${workspaceFolder}/app.js",
      "skipFiles": ["<node_internals>/**"]
    }
  ]
}
```

## Core Actions

```text
F5        Start or continue
F9        Toggle breakpoint
F10       Step over
F11       Step into
Shift+F11 Step out
Shift+F5  Stop
```

VS Code includes JavaScript, TypeScript and Node.js debugging; other runtimes can require extensions. Advanced configurations are stored in `.vscode/launch.json`. Use `preLaunchTask`, environment variables and compound configurations deliberately.
