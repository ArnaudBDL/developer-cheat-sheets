# Docker : Installation

## Verify Installation

```bash
docker --version
docker compose version
docker info
docker run --rm hello-world
```

## Docker Desktop

Docker Desktop provides Docker Engine, Docker CLI, Docker Compose and a graphical interface for macOS, Windows and Linux.

```bash
# macOS with Homebrew
brew install --cask docker

# Start Docker Desktop
open -a Docker
```

## Linux Service

```bash
sudo systemctl enable --now docker
sudo systemctl status docker
sudo usermod -aG docker "$USER"
```

Log out and back in after adding the current user to the `docker` group.

## Configuration

```bash
# Display client and server configuration
docker info

# Display Docker contexts
docker context ls

# Select a context
docker context use default
```
