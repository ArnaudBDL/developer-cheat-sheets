# Express : Installation

## Create a Project

```bash
mkdir application
cd application
npm init -y
npm install express
```

## Development Dependencies

```bash
npm install --save-dev eslint supertest
```

## package.json

```json
{
  "name": "application",
  "version": "1.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "start": "node src/server.js",
    "dev": "node --watch src/server.js",
    "test": "node --test"
  },
  "dependencies": {
    "express": "^5.0.0"
  }
}
```

## Verify

```bash
node --version
npm --version
npm list express
npm run dev
```
