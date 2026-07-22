# PHP : Composer

## Project Commands

```bash
composer init
composer install
composer update
composer require vendor/package
composer require --dev phpunit/phpunit
composer remove vendor/package
```

## composer.json

```json
{
  "name": "example/application",
  "require": {
    "php": "^8.3"
  },
  "require-dev": {
    "phpunit/phpunit": "^12.0"
  },
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  },
  "autoload-dev": {
    "psr-4": {
      "App\\Tests\\": "tests/"
    }
  },
  "scripts": {
    "test": "phpunit"
  },
  "config": {
    "sort-packages": true,
    "allow-plugins": {}
  }
}
```

## Autoloading

```php
require dirname(__DIR__) . '/vendor/autoload.php';
```

```bash
composer dump-autoload
composer dump-autoload --optimize
```

## Inspect and Validate

```bash
composer validate
composer show
composer outdated
composer why vendor/package
composer why-not vendor/package VERSION
composer check-platform-reqs
composer diagnose
composer audit
```

## Production Install

```bash
composer install \
  --no-dev \
  --prefer-dist \
  --no-interaction \
  --optimize-autoloader
```
