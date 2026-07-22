# Tauri : Windows

## Configured Window

```json
{
  "app": {
    "windows": [
      {
        "label": "main",
        "title": "Application",
        "width": 1280,
        "height": 800,
        "minWidth": 900,
        "minHeight": 600,
        "resizable": true,
        "fullscreen": false
      }
    ]
  }
}
```

## Frontend Window API

```typescript
import { getCurrentWindow } from '@tauri-apps/api/window'

const window = getCurrentWindow()
await window.minimize()
await window.maximize()
await window.unmaximize()
await window.setFullscreen(true)
await window.close()
```

## Rust Window Access

```rust
use tauri::Manager;

if let Some(window) = app.get_webview_window("main") {
    window.set_title("Application")?;
}
```

