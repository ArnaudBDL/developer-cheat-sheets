# Electron : Main Process

## Application Lifecycle

```javascript
const { app, BrowserWindow } = require('electron/main')
const path = require('node:path')

function createWindow() {
  const window = new BrowserWindow({
    webPreferences: {
      preload: path.join(__dirname, 'preload.js'),
      contextIsolation: true,
      nodeIntegration: false,
      sandbox: true
    }
  })

  window.loadFile('index.html')
}

app.whenReady().then(() => {
  createWindow()

  app.on('activate', () => {
    if (BrowserWindow.getAllWindows().length === 0) createWindow()
  })
})

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') app.quit()
})
```

## Paths

```javascript
const userData = app.getPath('userData')
const documents = app.getPath('documents')
const logs = app.getPath('logs')
```

