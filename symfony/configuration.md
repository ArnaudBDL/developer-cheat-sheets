# Symfony : Configuration

## Configuration Structure

```text
config/
├── bundles.php
├── packages/
├── routes/
├── routes.yaml
└── services.yaml
```

## Environment Variables

```dotenv
DATABASE_URL="postgresql://app:password@127.0.0.1:5432/app"
MAILER_DSN="smtp://localhost:1025"
```

```yaml
parameters:
  app.upload_directory: '%kernel.project_dir%/var/uploads'
```

## Inspect Configuration

```bash
php bin/console debug:config framework
php bin/console config:dump-reference framework
php bin/console debug:container --parameters
php bin/console debug:dotenv
php bin/console lint:yaml config/
php bin/console lint:container
```

## Environment-Specific Configuration

```text
config/packages/framework.yaml
config/packages/dev/framework.yaml
config/packages/prod/framework.yaml
config/packages/test/framework.yaml
```
