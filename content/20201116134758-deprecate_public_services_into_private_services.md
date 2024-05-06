---
id: 6ecb0d08-16f6-42c5-ac0d-916b875bc1ff
title: Deprecate Public Services Into Private Services
---

# Description

Deprecated public services and turns them into private

# Syntax

``` yaml
services:
    foo:
        # ...
        public: true
        tags:
            - { name: 'container.private', package: 'foo/bar', 'version': '1.2' }
```

If your application tries to get that service directly from the
container `($container->get('foo'))` you'll see the following error:

    Since foo/bar 1.2: Accessing the "foo" service directly from the container
    is deprecated, use dependency injection instead.
