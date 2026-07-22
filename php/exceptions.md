# PHP : Exceptions

## Throw and Catch

```php
try {
    $result = process($input);
} catch (InvalidArgumentException $exception) {
    echo $exception->getMessage(), PHP_EOL;
} finally {
    releaseResources();
}
```

## Custom Exception

```php
final class ConfigurationException extends RuntimeException
{
}

throw new ConfigurationException('Missing configuration');
```

## Multiple Exception Types

```php
try {
    execute();
} catch (NetworkException|TimeoutException $exception) {
    retry($exception);
}
```

## Exception Chaining

```php
try {
    $repository->save($entity);
} catch (PDOException $exception) {
    throw new RuntimeException('Unable to save entity', 0, $exception);
}
```

## Inspect

```php
$exception->getMessage();
$exception->getCode();
$exception->getFile();
$exception->getLine();
$exception->getTraceAsString();
$exception->getPrevious();
```
