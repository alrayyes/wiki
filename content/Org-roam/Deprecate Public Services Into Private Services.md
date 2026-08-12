---
publish: true
title: Deprecate Public Services Into Private Services
created: 2020-11-16T13:47:58
---

## Description

Deprecated public services and turns them into private

## Syntax

```yaml
services:
    foo:
        # ...
        public: true
        tags:
            - { name: 'container.private', package: 'foo/bar', 'version': '1.2' }
```

If your application tries to get that service directly from the container ~(\$container->get('foo'))~ you'll see the following error:

```
Since foo/bar 1.2: Accessing the "foo" service directly from the container
is deprecated, use dependency injection instead.
```
