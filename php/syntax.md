# PHP : Syntax

## Basic File

```php
<?php

declare(strict_types=1);

$message = 'Hello';
echo $message, PHP_EOL;
```

## Comments

```php
// Single-line comment
# Single-line comment
/* Multi-line comment */
```

## Output

```php
echo 'Value', PHP_EOL;
printf('Name: %s, count: %d%s', $name, $count, PHP_EOL);
var_dump($value);
print_r($array);
```

## Include Files

```php
require __DIR__ . '/bootstrap.php';
require_once __DIR__ . '/functions.php';
include __DIR__ . '/optional.php';
include_once __DIR__ . '/helpers.php';
```

## CLI Arguments

```php
<?php

declare(strict_types=1);

$script = $argv[0];
$arguments = array_slice($argv, 1);
printf('%s received %d arguments%s', $script, count($arguments), PHP_EOL);
```
