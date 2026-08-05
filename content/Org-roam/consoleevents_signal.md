---
publish: true
title: ConsoleEvents::SIGNAL
created: 2020-11-17T11:51:46
modified: 2026-08-05T10:26:50.497Z
---

# ConsoleEvents::SIGNAL

# Description

[Events](Events) to handle application command \[Console Signals]\(Console Signals).

# Syntax

// ...
use Symfony\Component\Console\Event\ConsoleSignalEvent;

class SignalSubscriber implements EventSubscriberInterface
{
// ...

```
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
```

}
