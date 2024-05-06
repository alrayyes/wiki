---
id: 03320caf-dc21-416f-9d74-dc1bc219101e
title: "ConsoleEvents::SIGNAL"
---

# Description

[Event](20201113175016-events) to handle application command
[signals](20201117114930-console_signals).

# Syntax

``` php
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
