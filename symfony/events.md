# Symfony : Events

## Event Subscriber

```php
namespace App\EventSubscriber;

use Symfony\Component\EventDispatcher\EventSubscriberInterface;
use Symfony\Component\HttpKernel\Event\RequestEvent;
use Symfony\Component\HttpKernel\KernelEvents;

final class RequestSubscriber implements EventSubscriberInterface
{
    public static function getSubscribedEvents(): array
    {
        return [KernelEvents::REQUEST => ['onRequest', 10]];
    }

    public function onRequest(RequestEvent $event): void
    {
        if (!$event->isMainRequest()) {
            return;
        }
    }
}
```

## Custom Event

```php
final readonly class OrderCreated
{
    public function __construct(public int $orderId)
    {
    }
}
```

```php
$eventDispatcher->dispatch(new OrderCreated($order->id()));
```

## Inspect Events

```bash
php bin/console debug:event-dispatcher
php bin/console debug:event-dispatcher kernel.request
```
