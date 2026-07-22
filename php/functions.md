# PHP : Functions

## Declaration

```php
function add(int $left, int $right): int
{
    return $left + $right;
}
```

## Named and Default Arguments

```php
function connect(string $host, int $port = 5432, bool $secure = true): void
{
    // ...
}

connect(host: 'database', secure: false);
```

## Variadic Arguments

```php
function total(int ...$values): int
{
    return array_sum($values);
}

$result = total(1, 2, 3);
```

## Closures and Arrow Functions

```php
$multiplier = 2;
$double = static fn (int $value): int => $value * $multiplier;

$filter = static function (array $items) use ($minimum): array {
    return array_filter($items, static fn (int $item): bool => $item >= $minimum);
};
```

## First-Class Callable

```php
$callback = strtoupper(...);
$result = array_map($callback, ['one', 'two']);
```
