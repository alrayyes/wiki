---
publish: true
aliases:
  - ConsoleEvents::SIGNAL
title: ConsoleEvents::SIGNAL
created: 2020-11-17T11:51:46
modified: 2026-08-12T09:44:58.317Z
---

# ConsoleEvents::SIGNAL

## Description

[[Events]] to handle application command [[Console Signals]].

## Syntax

```php
// ...
use Symfony\Component\Console\Event\ConsoleSignalEvent;

class SignalSubscriber implements EventSubscriberInterface
{
    // ...

    public function handleSignal(ConsoleSignalEvent $event)
    {
        $signal = $event->getHandlingSignal();

        // ...
    }

    public static function getSubscribedEvents()
    {
        return [
            ConsoleEvents::SIGNAL => 'handleSignal',
        ];
    }
}
```
