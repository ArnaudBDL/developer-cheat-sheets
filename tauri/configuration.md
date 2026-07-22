# Tauri : Configuration

## tauri.conf.json

```json
{
  "$schema": "https://schema.tauri.app/config/2",
  "productName": "Application",
  "version": "1.0.0",
  "identifier": "com.example.application",
  "build": {
    "beforeDevCommand": "npm run start",
    "devUrl": "http://localhost:4200",
    "beforeBuildCommand": "npm run build",
    "frontendDist": "../dist/application/browser"
  },
  "app": {
    "windows": [
      {
        "label": "main",
        "title": "Application",
        "width": 1280,
        "height": 800
      }
    ]
  },
  "bundle": {
    "active": true,
    "targets": "all"
  }
}
```

## Inspect

```bash
npm run tauri info
npm run tauri inspect
cargo metadata --format-version 1
```

