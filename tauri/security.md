# Tauri : Security

## Principles

```text
Minimize enabled plugins and permissions.
Separate capabilities by window and trust level.
Validate command arguments in Rust.
Load only trusted application content.
Define a restrictive Content Security Policy.
Keep Tauri, Rust crates and frontend dependencies updated.
Sign production bundles and update artifacts.
```

## CSP Example

```json
{
  "app": {
    "security": {
      "csp": "default-src 'self'; connect-src 'self' ipc: http://ipc.localhost; img-src 'self' asset: http://asset.localhost"
    }
  }
}
```

## Dependency Checks

```bash
cargo audit
cargo update
npm audit
npm outdated
```

