---
publish: true
title: abstraction
created: 2020-11-26T10:27:08
modified: 2026-08-12T10:31:55.384Z
---

# abstraction

## Origin

Latin abstrahere "drawm from"

## Definition

Hide implementation details from the user. For exapmle by extending classes.

## Examples

```typescript
abstract class Fish {
    swim() { return '>>>>>' }
}

class Shark extends Fish  {
    name: 'shark'
}

class Tuna extends Fish {
    name: 'tuna'
}
```
