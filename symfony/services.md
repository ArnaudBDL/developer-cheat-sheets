# Symfony : Services

## Automatic Registration

```yaml
# config/services.yaml
services:
  _defaults:
    autowire: true
    autoconfigure: true

  App\:
    resource: '../src/'
    exclude:
      - '../src/DependencyInjection/'
      - '../src/Entity/'
      - '../src/Kernel.php'
```

## Explicit Service

```yaml
services:
  App\Service\ReportGenerator:
    arguments:
      $outputDirectory: '%kernel.project_dir%/var/reports'
```

## Inspect Services

```bash
php bin/console debug:container
php bin/console debug:container App\Service\ReportGenerator
php bin/console debug:autowiring
php bin/console lint:container
```

## Service Alias

```yaml
services:
  App\Contract\NotifierInterface:
    alias: App\Service\EmailNotifier
```
