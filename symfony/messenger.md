# Symfony : Messenger

## Transport Configuration

```yaml
framework:
  messenger:
    failure_transport: failed
    transports:
      async: '%env(MESSENGER_TRANSPORT_DSN)%'
      failed: 'doctrine://default?queue_name=failed'
    routing:
      App\Message\GenerateReport: async
```

```dotenv
MESSENGER_TRANSPORT_DSN=doctrine://default?queue_name=async
```

## Message and Handler

```php
final readonly class GenerateReport
{
    public function __construct(public int $reportId)
    {
    }
}
```

```php
use Symfony\Component\Messenger\Attribute\AsMessageHandler;

#[AsMessageHandler]
final class GenerateReportHandler
{
    public function __invoke(GenerateReport $message): void
    {
        // ...
    }
}
```

## Dispatch and Consume

```php
$messageBus->dispatch(new GenerateReport($reportId));
```

```bash
php bin/console messenger:consume async -vv
php bin/console messenger:failed:show
php bin/console messenger:failed:retry
php bin/console messenger:failed:remove
```
