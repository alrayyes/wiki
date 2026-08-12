---
publish: true
title: LogoutEvent
created: 2020-11-16T13:39:07
---

# LogoutEvent

## Description

Replaces ~LogoutSuccessHandlerInterface~ and ~LogougHandlerInterface~

## Syntax

```yaml
# config/services.yaml
services:
    # ...
    App\EventListener\MyCutomLogoutListener:
        tags:
            - name: 'kernel.event_listener'
              event: 'Symfony\Component\Security\Http\Event\LogoutEvent'
              dispatcher: security.event_dispatcher.main
```
