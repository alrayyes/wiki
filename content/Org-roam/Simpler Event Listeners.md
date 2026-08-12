---
publish: true
title: Simpler Event Listeners
created: 2020-11-13T18:02:27
---

# Simpler Event Listeners

## Syntax

```yaml
# config/services.yaml
services:
  App\EventListener\MyRequestListener:
    tags:
      - { name: kernel.event_listener }
```

```php
namespace App\EventListener;

use Symfony\Component\HttpKernel\Event\RequestEvent;

final class MyRequestListener
{
    public function __invoke(RequestEvent $event): void
    {
        // ...
    }
}
```
