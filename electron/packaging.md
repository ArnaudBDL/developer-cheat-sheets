# Electron : Packaging

## Electron Forge

```bash
npm install --save-dev @electron-forge/cli
npx electron-forge import
npm run package
npm run make
```

## Package Scripts

```json
{
  "scripts": {
    "start": "electron-forge start",
    "package": "electron-forge package",
    "make": "electron-forge make"
  }
}
```

## Release Checks

```text
Test packaged builds on every target operating system. Configure application identifiers, icons, code signing and platform-specific metadata. Rebuild native modules for the packaged Electron runtime.
```

