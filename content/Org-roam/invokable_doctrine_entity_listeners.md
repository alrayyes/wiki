---
publish: true
title: Invokable Doctrine Entity Listeners
created: 2020-11-13T18:07:22
modified: 2026-08-05T07:58:56.686Z
---

# Invokable Doctrine Entity Listeners

# Syntax

namespace App\EventListener;

use App\Entity\User;
use Doctrine\Common\Persistence\Event\LifecycleEventArgs;

class UserChangedNotifier
{
public function \_\_invoke(User $user, LifecycleEventArgs $event)
{
// ...
}
}

services:
\# ...

```
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
