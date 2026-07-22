# Node.js : Package JSON

## Basic File

```json
{
  "name": "application",
  "version": "1.0.0",
  "private": true,
  "type": "module",
  "engines": {
    "node": ">=22"
  },
  "scripts": {
    "start": "node src/app.js",
    "dev": "node --watch src/app.js",
    "test": "node --test",
    "lint": "eslint ."
  },
  "dependencies": {},
  "devDependencies": {}
}
```

## Entry Points

```json
{
  "main": "./dist/index.cjs",
  "module": "./dist/index.js",
  "types": "./dist/index.d.ts",
  "exports": {
    ".": {
      "import": "./dist/index.js",
      "require": "./dist/index.cjs"
    }
  }
}
```

## Package Scripts

```bash
npm run SCRIPT
npm run SCRIPT -- --option value
npm pkg get scripts
npm pkg set scripts.check="npm test"
```

## Lock File

Commit `package-lock.json` for reproducible application dependency resolution and use `npm ci` in automated environments.
