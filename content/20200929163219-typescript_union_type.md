---
id: 2dae9e2e-90c4-4d1b-a992-baacaa053b21
title: TypeScript Union Type
---

# Syntax

``` typescript
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
