# PHP : Control Structures

## Conditions

```php
if ($score >= 80) {
    $grade = 'A';
} elseif ($score >= 60) {
    $grade = 'B';
} else {
    $grade = 'C';
}
```

## match

```php
$label = match ($status) {
    200, 201 => 'success',
    404 => 'not-found',
    500 => 'server-error',
    default => 'unknown',
};
```

## Loops

```php
for ($index = 0; $index < 10; $index++) {
    echo $index, PHP_EOL;
}

foreach ($items as $key => $item) {
    printf('%s: %s%s', $key, $item, PHP_EOL);
}

while ($condition) {
    // ...
}
```

## switch

```php
switch ($command) {
    case 'start':
        startApplication();
        break;
    case 'stop':
        stopApplication();
        break;
    default:
        throw new InvalidArgumentException('Unknown command');
}
```

## Loop Control

```php
continue;
break;
continue 2;
break 2;
```
