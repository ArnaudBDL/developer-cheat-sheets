# Tauri : Commands

## Define Commands

```rust
#[tauri::command]
fn greet(name: String) -> String {
    format!("Hello, {name}!")
}

#[tauri::command]
async fn load_settings() -> Result<String, String> {
    Ok("{}".to_string())
}
```

## Register Commands

```rust
tauri::Builder::default()
    .invoke_handler(tauri::generate_handler![greet, load_settings])
    .run(tauri::generate_context!())
    .expect("error while running Tauri application");
```

## Invoke from Frontend

```typescript
import { invoke } from '@tauri-apps/api/core'

const message = await invoke<string>('greet', { name: 'Arnaud' })
const settings = await invoke<string>('load_settings')
```

## Rule

```text
Use serializable command parameters and return values. Validate all frontend-provided values in Rust before performing privileged operations.
```

