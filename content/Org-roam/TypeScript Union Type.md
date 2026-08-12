---
publish: true
title: TypeScript Union Type
created: 2020-09-29T16:32:19
modified: 2026-08-12T09:32:15.643Z
---

# TypeScript Union Type

## Syntax

```typescript
function formatCommandline(command: string[]|string) {
    var line = '';
    if (typeof command === 'string') {
        line = command.trim();
    } else {
        line = command.join(' ').trim();
    }

    // Do stuff with line: string
}
```
