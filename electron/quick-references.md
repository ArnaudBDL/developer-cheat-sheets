# Electron : Quick References

## Main process

```javascript
const { app, BrowserWindow } = require("electron");

app.whenReady().then(() => {
  const window = new BrowserWindow({
    webPreferences: { preload: PRELOAD_PATH, contextIsolation: true }
  });
  window.loadFile("index.html");
});
```

## IPC

```javascript
// main
ipcMain.handle("read-data", async () => loadData());

// renderer
const data = await window.api.readData();
```

## Packaging

```bash
npm run start
npm run package
npm run make
```
