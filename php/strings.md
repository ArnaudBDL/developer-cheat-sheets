# PHP : Strings

## Quotes and Interpolation

```php
$literal = 'Hello $name';
$interpolated = "Hello {$name}";
$multiline = <<<TEXT
Hello {$name}
Welcome back.
TEXT;
```

## Common Operations

```php
$length = strlen($value);
$trimmed = trim($value);
$lower = strtolower($value);
$upper = strtoupper($value);
$part = substr($value, 0, 10);
$replaced = str_replace('old', 'new', $value);
$contains = str_contains($value, 'needle');
$starts = str_starts_with($value, 'prefix');
$ends = str_ends_with($value, 'suffix');
```

## Split and Join

```php
$parts = explode(',', $csv);
$csv = implode(',', $parts);
```

## Formatting

```php
$message = sprintf('User %s has %d items', $name, $count);
printf('%s%s', $message, PHP_EOL);
```

## Multibyte Strings

```php
$length = mb_strlen($value, 'UTF-8');
$part = mb_substr($value, 0, 10, 'UTF-8');
$lower = mb_strtolower($value, 'UTF-8');
```
