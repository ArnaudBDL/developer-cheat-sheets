# TypeScript : Installation

## Local Installation

```bash
mkdir application
cd application
npm init -y
npm install --save-dev typescript
npx tsc --version
```

## Initialize a Project

```bash
npx tsc --init
```

## Compile

```bash
npx tsc
npx tsc --noEmit
npx tsc --watch
npx tsc src/index.ts --outDir dist
```

## Package Scripts

```json
{
  "scripts": {
    "build": "tsc",
    "check": "tsc --noEmit",
    "watch": "tsc --watch"
  }
}
```
