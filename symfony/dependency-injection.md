# Symfony : Dependency Injection

## Constructor Injection

```php
final class OrderService
{
    public function __construct(
        private readonly OrderRepository $repository,
        private readonly LoggerInterface $logger,
    ) {
    }
}
```

## Bind Named Arguments

```yaml
services:
  _defaults:
    bind:
      string $applicationName: 'Application'
      string $uploadDirectory: '%kernel.project_dir%/var/uploads'
```

## Tagged Iterator

```php
use Symfony\Component\DependencyInjection\Attribute\TaggedIterator;

public function __construct(
    #[TaggedIterator('app.processor')]
    private readonly iterable $processors,
) {
}
```

```yaml
services:
  App\Processor\JsonProcessor:
    tags: ['app.processor']
```

## Inspect

```bash
php bin/console debug:autowiring LoggerInterface
php bin/console debug:container --tag=app.processor
php bin/console lint:container
```
