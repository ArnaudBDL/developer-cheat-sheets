# Node.js : Installation

## Verify Installation

```bash
node --version
npm --version
npx --version
node --help
```

## Install with nvm

```bash
nvm install --lts
nvm use --lts
nvm alias default lts/*
nvm current
nvm list
```

## macOS

```bash
brew install node
brew upgrade node
```

## Run Code

```bash
node app.js
node --watch app.js
node -e "console.log(process.version)"
node
```

## Inspect Runtime

```bash
node -p "process.versions"
node -p "process.execPath"
node -p "process.platform"
node -p "process.arch"
```
