---
publish: true
title: TypeScript Union Type
created: 2020-09-29T16:32:19
---

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
