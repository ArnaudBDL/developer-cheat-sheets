# Docker : Registry

## Authentication

```bash
docker login
docker login registry.example.com
docker logout
docker logout registry.example.com
```

## Tag and Push

```bash
docker tag my-app:latest registry.example.com/team/my-app:1.0.0
docker push registry.example.com/team/my-app:1.0.0
```

## Pull

```bash
docker pull nginx:alpine
docker pull registry.example.com/team/my-app:1.0.0
```

## Run a Local Registry

```bash
docker run -d   --name registry   --restart always   -p 5000:5000   -v registry-data:/var/lib/registry   registry:2

docker tag my-app:latest localhost:5000/my-app:latest
docker push localhost:5000/my-app:latest
docker pull localhost:5000/my-app:latest
```

## Credential Input

```bash
printf '%s' "$REGISTRY_TOKEN" |   docker login registry.example.com --username "$REGISTRY_USER" --password-stdin
```
