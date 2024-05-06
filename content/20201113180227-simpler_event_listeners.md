---
id: 0ada3ab8-c8d8-4803-9c7d-7e044533f793
title: Simpler Event Listeners
---

# Syntax

``` yaml
# config/services.yaml
services:
  App\EventListener\MyRequestListener:
    tags:
      - { name: kernel.event_listener }
```

``` php
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
