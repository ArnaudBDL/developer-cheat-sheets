# Docker : Security

## Runtime Hardening

```bash
docker run --rm   --read-only   --tmpfs /tmp   --cap-drop ALL   --security-opt no-new-privileges:true   --user 1000:1000   --memory 512m   --cpus 1   IMAGE
```

## Secrets

Do not store secrets in images, Dockerfiles, build arguments or committed environment files.

```yaml
services:
  app:
    image: my-app
    secrets:
      - database-password

secrets:
  database-password:
    file: ./secrets/database-password.txt
```

## Secure Dockerfile

```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY --chown=node:node package*.json ./
RUN npm ci --omit=dev && npm cache clean --force
COPY --chown=node:node . .
USER node
CMD ["node", "server.js"]
```

## Inspection

```bash
docker inspect IMAGE
docker history --no-trunc IMAGE
docker image inspect IMAGE --format '{{json .Config.User}}'
docker scout quickview IMAGE
docker scout cves IMAGE
```

## Security Checklist

- Use trusted and minimal base images.
- Pin image versions or digests where reproducibility matters.
- Rebuild images regularly with updated dependencies.
- Run containers as a non-root user.
- Remove unnecessary Linux capabilities.
- Use read-only filesystems where possible.
- Do not expose the Docker socket to untrusted containers.
- Restrict published ports to the required interfaces.
- Set CPU and memory limits.
- Scan images before deployment.
