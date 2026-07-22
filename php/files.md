# PHP : Files

## Read and Write

```php
$content = file_get_contents($path);
file_put_contents($path, $content, LOCK_EX);
file_put_contents($logPath, $message . PHP_EOL, FILE_APPEND | LOCK_EX);
```

## Stream Access

```php
$handle = fopen($path, 'rb');
if ($handle === false) {
    throw new RuntimeException('Unable to open file');
}

try {
    while (($line = fgets($handle)) !== false) {
        echo $line;
    }
} finally {
    fclose($handle);
}
```

## Paths and Directories

```php
$path = __DIR__ . '/data/file.txt';
$directory = dirname($path);
$filename = basename($path);
$exists = is_file($path);
$isDirectory = is_dir($directory);
mkdir($directory, 0755, true);
```

## JSON

```php
$data = json_decode($json, true, flags: JSON_THROW_ON_ERROR);
$json = json_encode($data, JSON_THROW_ON_ERROR | JSON_PRETTY_PRINT);
```

## Temporary Files

```php
$path = tempnam(sys_get_temp_dir(), 'app-');
$handle = tmpfile();
```
