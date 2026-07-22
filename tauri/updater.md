# Tauri : Updater

## Add Plugin

```bash
npm run tauri add updater
npm run tauri add process
```

## Frontend Check

```typescript
import { check } from '@tauri-apps/plugin-updater'
import { relaunch } from '@tauri-apps/plugin-process'

const update = await check()
if (update) {
  await update.downloadAndInstall(event => {
    console.log(event)
  })
  await relaunch()
}
```

## Configuration

```json
{
  "plugins": {
    "updater": {
      "endpoints": [
        "https://example.com/releases/latest.json"
      ],
      "pubkey": "UPDATER_PUBLIC_KEY"
    }
  }
}
```

## Signing

```bash
npm run tauri signer generate
npm run tauri signer sign PATH_TO_ARTIFACT
```

## Rule

```text
Use HTTPS endpoints, verify signatures with the configured public key, protect the private signing key, and test upgrades from previously released versions.
```

