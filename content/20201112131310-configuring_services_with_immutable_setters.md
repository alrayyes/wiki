---
id: 51f4dd9e-6f11-485d-8544-f302e71fc036
title: Configuring Services With Immutable Setters
---

# Description

A common need in some Symfony applications is to use immutable services
while still using traits for composing their optional features. Although
the Symfony service container supports setter injection, they have some
drawbacks (e.g. setters can be called more than just at the time of
construction so you cannot be sure the dependency is not replaced during
the lifetime of the object).

A pattern to solve this problem are "wither methods". These methods
typically use the with word as the prefix of their names (e.g.
withPropertyName()) and they return a copy of an instance of an
immutable class with only that one property changed:

``` php
class MyService
{
    use LoggerAwareTrait;

    // ...
}

trait LoggerAwareTrait
{
    private $logger;

    public function withLogger(LoggerInterface $logger)
    {
        $new = clone $this;
        $new->logger = $logger;

        return $new;
    }
}

$service = new MyService();
$service = $service->withLogger($logger);
```

# Syntax

``` yaml
# config/services.yaml
services:
    MyService:
        # ...
        calls:
            # the TRUE argument turns this into a wither method
            - ['withLogger', ['@logger'], true]
```

``` php
class MyService
{
    // ...

    /**
     * @required
     * @return static
     */
    public function withLogger(LoggerInterface $logger)
    {
        // ...
    }
}
```
