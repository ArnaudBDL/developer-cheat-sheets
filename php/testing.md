# PHP : Testing

## Install PHPUnit

```bash
composer require --dev phpunit/phpunit
vendor/bin/phpunit --version
```

## Basic Test

```php
<?php

declare(strict_types=1);

namespace App\Tests;

use App\Calculator;
use PHPUnit\Framework\TestCase;

final class CalculatorTest extends TestCase
{
    public function testAddsTwoNumbers(): void
    {
        $calculator = new Calculator();

        self::assertSame(5, $calculator->add(2, 3));
    }
}
```

## Exceptions

```php
public function testRejectsInvalidInput(): void
{
    $this->expectException(InvalidArgumentException::class);

    service()->execute('invalid');
}
```

## Data Provider

```php
use PHPUnit\Framework\Attributes\DataProvider;

#[DataProvider('values')]
public function testAdds(int $left, int $right, int $expected): void
{
    self::assertSame($expected, $left + $right);
}

public static function values(): iterable
{
    yield 'positive' => [2, 3, 5];
    yield 'negative' => [-2, 1, -1];
}
```

## Run Tests

```bash
vendor/bin/phpunit
vendor/bin/phpunit tests/CalculatorTest.php
vendor/bin/phpunit --filter testAddsTwoNumbers
vendor/bin/phpunit --testdox
vendor/bin/phpunit --coverage-text
```
