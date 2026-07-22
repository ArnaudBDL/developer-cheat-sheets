# PHP : Types

## Scalar Types

```php
$enabled = true;
$count = 42;
$price = 19.99;
$name = 'PHP';
```

## Compound and Special Types

```php
$items = ['one', 'two'];
$object = new stdClass();
$value = null;
$callback = static fn (int $value): int => $value * 2;
```

## Type Declarations

```php
function formatName(string $firstName, ?string $lastName = null): string
{
    return trim($firstName . ' ' . ($lastName ?? ''));
}
```

## Union and Intersection Types

```php
function normalize(int|float $value): float
{
    return (float) $value;
}

function process(Countable&Iterator $items): void
{
    foreach ($items as $item) {
        // ...
    }
}
```

## Inspect and Convert

```php
$type = get_debug_type($value);
$isString = is_string($value);
$isIterable = is_iterable($value);
$integer = (int) $value;
$string = (string) $value;
```
