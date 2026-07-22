# SQLite : Installation

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install sqlite3
sqlite3 --version
```

## Fedora

```bash
sudo dnf install sqlite
sqlite3 --version
```

## Arch Linux

```bash
sudo pacman -S sqlite
sqlite3 --version
```

## macOS

```bash
brew install sqlite
brew upgrade sqlite
sqlite3 --version
```

## Verify Features

```bash
sqlite3 --version
sqlite3 :memory: 'SELECT sqlite_version();'
sqlite3 :memory: 'PRAGMA compile_options;'
```

## Create a Database

```bash
sqlite3 application.db
```
