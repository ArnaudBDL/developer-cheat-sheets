# Electron : Renderer Process

## Renderer Entry

```javascript
const button = document.querySelector('#open-file')
const output = document.querySelector('#output')

button.addEventListener('click', async () => {
  const result = await window.desktop.openFile()
  output.textContent = result?.path ?? 'No file selected'
})
```

## Rules

```text
Use browser APIs for UI work. Do not expose Node.js directly. Call only the narrow preload APIs required by the interface.
```

