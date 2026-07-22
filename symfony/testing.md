# Symfony : Testing

## Install Test Tools

```bash
composer require --dev symfony/test-pack
php bin/phpunit --version
```

## Unit Test

```php
use PHPUnit\Framework\TestCase;

final class CalculatorTest extends TestCase
{
    public function testAddition(): void
    {
        self::assertSame(5, (new Calculator())->add(2, 3));
    }
}
```

## Kernel Test

```php
use Symfony\Bundle\FrameworkBundle\Test\KernelTestCase;

final class ServiceTest extends KernelTestCase
{
    public function testService(): void
    {
        self::bootKernel();
        $service = self::getContainer()->get(ReportGenerator::class);

        self::assertInstanceOf(ReportGenerator::class, $service);
    }
}
```

## Functional Test

```php
use Symfony\Bundle\FrameworkBundle\Test\WebTestCase;

final class HealthControllerTest extends WebTestCase
{
    public function testHealth(): void
    {
        $client = self::createClient();
        $client->request('GET', '/health');

        self::assertResponseIsSuccessful();
        self::assertResponseFormatSame('json');
    }
}
```

```bash
php bin/phpunit
php bin/phpunit --filter HealthControllerTest
```
