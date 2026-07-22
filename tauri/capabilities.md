# Tauri : Capabilities

## Capability File

```json
{
  "$schema": "../gen/schemas/desktop-schema.json",
  "identifier": "main-capability",
  "description": "Permissions for the main window",
  "windows": ["main"],
  "permissions": [
    "core:default",
    "dialog:allow-open",
    "fs:allow-read-text-file",
    "allow-load-settings"
  ]
}
```

## Manage Capabilities

```bash
npm run tauri capability new main-capability
npm run tauri capability --help
npm run tauri permission add dialog:allow-open
```

## Rule

```text
Split capabilities by window or webview trust boundary. Avoid broad permissions when a restricted command or path scope is sufficient.
```

