# PHP : Quick References

## CLI

```bash
php -v
php -m
php -i
php -S localhost:8000 -t public
php -l file.php
```

## Composer

```bash
composer install
composer update
composer require vendor/package
composer dump-autoload
composer audit
```

## Language

```php
$value = $condition ? $a : $b;
$result = $value ?? $default;
$items = array_map(fn ($item) => $item->id, $objects);
[$first, $second] = $values;
```
