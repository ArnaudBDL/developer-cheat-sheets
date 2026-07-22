# PHP : Operators

## Arithmetic

```php
$sum = $a + $b;
$difference = $a - $b;
$product = $a * $b;
$quotient = $a / $b;
$remainder = $a % $b;
$power = $a ** $b;
```

## Comparison

```php
$a === $b;
$a !== $b;
$a <=> $b;
$a < $b;
$a >= $b;
```

Prefer strict comparison with `===` and `!==` when type coercion is not intended.

## Logical

```php
$valid = $enabled && $authorized;
$allowed = $admin || $owner;
$disabled = !$enabled;
```

## Null Coalescing and Ternary

```php
$name = $input['name'] ?? 'Anonymous';
$status = $enabled ? 'enabled' : 'disabled';
$value ??= 'default';
```

## String and Array Operators

```php
$fullName = $firstName . ' ' . $lastName;
$message .= PHP_EOL;
$combined = $left + $right;
```

## Nullsafe Operator

```php
$country = $user?->address()?->country();
```
