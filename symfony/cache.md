# Symfony : Cache

## Cache Configuration

```yaml
framework:
  cache:
    app: cache.adapter.filesystem
    pools:
      app.reports_cache:
        adapter: cache.app
        default_lifetime: 3600
```

## Use CacheInterface

```php
use Symfony\Contracts\Cache\CacheInterface;
use Symfony\Contracts\Cache\ItemInterface;

$value = $cache->get('report.' . $reportId, function (ItemInterface $item) use ($reportId): array {
    $item->expiresAfter(3600);
    $item->tag(['report', 'report.' . $reportId]);

    return $this->loadReport($reportId);
});
```

## Invalidate

```php
$cache->delete('report.' . $reportId);
$tagAwareCache->invalidateTags(['report.' . $reportId]);
```

## Commands

```bash
php bin/console cache:clear
php bin/console cache:warmup
php bin/console cache:pool:list
php bin/console cache:pool:clear cache.app
php bin/console cache:pool:delete cache.app KEY
```
