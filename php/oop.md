# PHP : Object-Oriented Programming

## Class

```php
final class User
{
    public function __construct(
        private readonly int $id,
        private string $name,
    ) {
    }

    public function id(): int
    {
        return $this->id;
    }

    public function rename(string $name): void
    {
        $this->name = $name;
    }
}
```

## Inheritance and Interfaces

```php
interface Logger
{
    public function log(string $message): void;
}

abstract class AbstractLogger implements Logger
{
    protected function format(string $message): string
    {
        return '[' . date(DATE_ATOM) . '] ' . $message;
    }
}
```

## Trait

```php
trait Timestamped
{
    private DateTimeImmutable $createdAt;

    private function initializeTimestamp(): void
    {
        $this->createdAt = new DateTimeImmutable();
    }
}
```

## Enums

```php
enum Status: string
{
    case Draft = 'draft';
    case Published = 'published';
}
```

## Anonymous Class

```php
$logger = new class implements Logger {
    public function log(string $message): void
    {
        echo $message, PHP_EOL;
    }
};
```
