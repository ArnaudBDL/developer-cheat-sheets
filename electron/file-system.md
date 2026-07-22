# Electron : File System

## Read and Write in Main

```javascript
const fs = require('node:fs/promises')

ipcMain.handle('file:read-text', async (event, filePath) => {
  validateSender(event.senderFrame)
  validateApprovedPath(filePath)
  return fs.readFile(filePath, 'utf8')
})

ipcMain.handle('file:write-text', async (event, filePath, content) => {
  validateSender(event.senderFrame)
  validateApprovedPath(filePath)
  await fs.writeFile(filePath, content, { encoding: 'utf8', flag: 'w' })
  return true
})
```

## Application Data

```javascript
const dataDirectory = app.getPath('userData')
const settingsPath = path.join(dataDirectory, 'settings.json')
await fs.mkdir(dataDirectory, { recursive: true })
```

## Rules

```text
Resolve and validate paths in the main process. Restrict operations to approved directories or user-selected files. Never accept arbitrary filesystem commands from a renderer.
```

