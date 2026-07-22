# Docker : Dockerfile

## Common Instructions

```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --omit=dev
COPY . .
ENV NODE_ENV=production
EXPOSE 3000
USER node
CMD ["node", "server.js"]
```

## Multi-Stage Build

```dockerfile
FROM node:22-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine AS runtime
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
```

## Build Arguments

```dockerfile
ARG APP_VERSION=development
ENV APP_VERSION=${APP_VERSION}
LABEL org.opencontainers.image.version=${APP_VERSION}
```

```bash
docker build --build-arg APP_VERSION=1.0.0 -t my-app:1.0.0 .
```

## Health Check

```dockerfile
HEALTHCHECK --interval=30s --timeout=3s --retries=3   CMD wget --quiet --tries=1 --spider http://localhost:3000/health || exit 1
```

## .dockerignore

```text
.git
.github
node_modules
vendor
coverage
dist
.env
*.log
```
