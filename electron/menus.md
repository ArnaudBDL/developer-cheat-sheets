# Electron : Menus

## Application Menu

```javascript
const { Menu } = require('electron/main')

const template = [
  {
    label: 'File',
    submenu: [
      { role: 'quit' }
    ]
  },
  {
    label: 'Edit',
    submenu: [
      { role: 'undo' },
      { role: 'redo' },
      { type: 'separator' },
      { role: 'copy' },
      { role: 'paste' }
    ]
  }
]

Menu.setApplicationMenu(Menu.buildFromTemplate(template))
```

## Context Menu

```javascript
const menu = Menu.buildFromTemplate([
  { role: 'copy' },
  { role: 'paste' },
  { type: 'separator' },
  { label: 'Refresh', click: () => reloadData() }
])

menu.popup({ window: mainWindow })
```

