# Tauri : File System

## Add Plugin

```bash
npm run tauri add fs
```

## Frontend API

```typescript
import { BaseDirectory, readTextFile, writeTextFile } from '@tauri-apps/plugin-fs'

const content = await readTextFile('settings.json', {
  baseDir: BaseDirectory.AppConfig
})

await writeTextFile('settings.json', content, {
  baseDir: BaseDirectory.AppConfig
})
```

## Rust Paths

```rust
use tauri::Manager;

let config_dir = app.path().app_config_dir()?;
let data_dir = app.path().app_data_dir()?;
```

## Rule

```text
Grant only required filesystem scopes. Prefer application directories or paths explicitly selected by the user. Validate paths before native access.
```

