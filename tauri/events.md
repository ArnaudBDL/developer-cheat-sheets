# Tauri : Events

## Listen in Frontend

```typescript
import { listen } from '@tauri-apps/api/event'

const unlisten = await listen<{ ready: boolean }>('application:status', event => {
  console.log(event.payload.ready)
})

unlisten()
```

## Emit from Frontend

```typescript
import { emit } from '@tauri-apps/api/event'

await emit('frontend:ready', { timestamp: Date.now() })
```

## Emit from Rust

```rust
use tauri::Emitter;

app.emit("application:status", serde_json::json!({
    "ready": true
}))?;
```

## Rule

```text
Use commands for request-response operations and events for notifications. Keep event names namespaced and remove frontend listeners when components are destroyed.
```

