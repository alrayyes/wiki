---
id: f5d0ea95-75b4-48e9-99b4-7e420fd40956
title: Invokable Doctrine Entity Listeners
---

# Syntax

``` php
namespace App\EventListener;

use App\Entity\User;
use Doctrine\Common\Persistence\Event\LifecycleEventArgs;

class UserChangedNotifier
{
    public function __invoke(User $user, LifecycleEventArgs $event)
    {
        // ...
    }
}
```

``` yaml
services:
    # ...

    App\EventListener\UserChangedNotifier:
        tags:
            -
                name: 'doctrine.orm.entity_listener'
                entity: 'App\Entity\User'
                # before, when not defining the method name, Symfony looked for
                # a method called after the event (e.g. 'postUpdate()') Now it
                # will also look for an '__invoke()' method
                event: 'postUpdate'
```
