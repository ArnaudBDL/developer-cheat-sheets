# Tauri : Build

## Development and Release

```bash
npm run tauri dev
npm run tauri build
npm run tauri build -- --debug
npm run tauri info
```

## Bundle Configuration

```json
{
  "bundle": {
    "active": true,
    "targets": "all",
    "icon": [
      "icons/32x32.png",
      "icons/128x128.png",
      "icons/icon.icns",
      "icons/icon.ico"
    ]
  }
}
```

## Artifacts

```text
src-tauri/target/release/
src-tauri/target/release/bundle/
```

## Release Checks

```text
Build on each target platform, configure signing, inspect generated bundles, test installation and uninstallation, and verify the packaged frontend path.
```

