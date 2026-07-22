# PHP : Namespaces

## Declare a Namespace

```php
<?php

declare(strict_types=1);

namespace App\Service;

final class UserService
{
}
```

## Import Symbols

```php
use App\Contract\Logger;
use App\Entity\User;
use App\Service\Mailer as ApplicationMailer;
use function App\Support\normalize;
use const App\Support\DEFAULT_LIMIT;
```

## Group Imports

```php
use App\Entity\{Order, Product, User};
```

## Fully Qualified Names

```php
$date = new \DateTimeImmutable();
$class = \App\Service\UserService::class;
$currentNamespace = __NAMESPACE__;
```

## PSR-4 Mapping

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

```bash
composer dump-autoload
```
