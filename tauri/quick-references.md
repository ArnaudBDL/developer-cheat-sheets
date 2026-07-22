# Tauri : Quick References

## Project

```bash
npm create tauri-app@latest
npm run tauri dev
npm run tauri build
npm run tauri info
```

## Invoke command

```typescript
import { invoke } from "@tauri-apps/api/core";
const result = await invoke<string>("command_name", { value });
```

## Rust command

```rust
#[tauri::command]
fn command_name(value: String) -> Result<String, String> {
    Ok(value)
}
```
