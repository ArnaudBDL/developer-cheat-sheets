# PHP : Arrays

## Indexed and Associative Arrays

```php
$colors = ['red', 'green', 'blue'];
$user = [
    'id' => 42,
    'name' => 'Arnaud',
    'active' => true,
];
```

## Access and Update

```php
$first = $colors[0];
$name = $user['name'] ?? 'Unknown';
$colors[] = 'orange';
$user['active'] = false;
unset($user['active']);
```

## Transform and Filter

```php
$doubled = array_map(static fn (int $value): int => $value * 2, $values);
$active = array_filter($users, static fn (array $user): bool => $user['active']);
$total = array_reduce($values, static fn (int $sum, int $value): int => $sum + $value, 0);
```

## Merge, Search and Sort

```php
$merged = array_merge($first, $second);
$exists = array_key_exists('name', $user);
$found = in_array('green', $colors, true);
sort($colors);
ksort($user);
```

## Destructuring

```php
[$first, $second] = $values;
['id' => $id, 'name' => $name] = $user;
```
