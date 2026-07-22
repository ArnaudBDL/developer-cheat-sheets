# Electron : Windows

## Create a Window

```javascript
const mainWindow = new BrowserWindow({
  width: 1280,
  height: 800,
  minWidth: 900,
  minHeight: 600,
  show: false,
  webPreferences: {
    preload: path.join(__dirname, 'preload.js'),
    contextIsolation: true,
    nodeIntegration: false,
    sandbox: true
  }
})

mainWindow.once('ready-to-show', () => mainWindow.show())
mainWindow.loadFile('index.html')
```

## Window APIs

```javascript
mainWindow.maximize()
mainWindow.unmaximize()
mainWindow.minimize()
mainWindow.setFullScreen(true)
mainWindow.close()
BrowserWindow.getAllWindows()
```

## Child Window

```javascript
const preferences = new BrowserWindow({
  parent: mainWindow,
  modal: true,
  width: 640,
  height: 480
})
```

