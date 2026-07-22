# Tauri : Troubleshooting

## Environment Information

```bash
npm run tauri info
rustc --version
cargo --version
node --version
npm --version
```

## Verbose Development

```bash
RUST_LOG=debug npm run tauri dev
RUST_BACKTRACE=1 npm run tauri dev
cargo check --manifest-path src-tauri/Cargo.toml
```

## Common Problems

```text
Command not found
  Check #[tauri::command], generate_handler registration and command spelling.

Permission denied
  Check plugin registration, permission identifier, capability membership and window label.

Blank window
  Check devUrl, frontendDist, frontend build output and browser console.

Plugin API unavailable
  Check Rust crate, frontend package, Builder registration and capability permission.

Build failure
  Check platform prerequisites, Rust target, native dependencies and CLI information.

Updater failure
  Check endpoint metadata, signature, public key, platform artifact and application version.
```

## Clean Build

```bash
rm -rf src-tauri/target
cargo clean --manifest-path src-tauri/Cargo.toml
npm run tauri build
```

