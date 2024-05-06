---
id: 6a54254e-2dae-47e5-8966-075e1bc1b7fa
title: Subscribing to events in the micro kernel
---

# Introduction

From [Symfony 4.0](20201109140137-symfony_4_0) it's possible to
subscribe to events using the `EventSubscriberInterface` Interface

# Syntax

``` php
// src/Kernel.php
namespace App;

use App\Exception\DangerException;
use Symfony\Bundle\FrameworkBundle\Kernel\MicroKernelTrait;
use Symfony\Component\EventDispatcher\EventSubscriberInterface;
use Symfony\Component\HttpKernel\Event\GetResponseForExceptionEvent;
use Symfony\Component\HttpKernel\Kernel as BaseKernel;
use Symfony\Component\HttpKernel\KernelEvents;

class Kernel extends BaseKernel implements EventSubscriberInterface
{
    use MicroKernelTrait;

    // ...

    public static function getSubscribedEvents()
    {
        return [KernelEvents::EXCEPTION => 'handleExceptions'];
    }

    public function handleExceptions(GetResponseForExceptionEvent $event)
    {
        if ($event->getException() instanceof DangerException) {
            $event->setResponse(Response::create('It\'s dangerous to go alone. Take this ⚔'));
        }

        // ...
    }
}
```
