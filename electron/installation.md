# Electron : Installation

## Create Project

```bash
mkdir electron-app
cd electron-app
npm init -y
npm install --save-dev electron
```

## Package Scripts

```json
{
  "main": "src/main.js",
  "scripts": {
    "start": "electron .",
    "dev": "electron ."
  }
}
```

## Run and Inspect

```bash
npm start
npx electron --version
npx electron . --enable-logging
```

