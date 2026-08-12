---
publish: true
title: react-jsx
created: 2020-11-30T08:52:53
modified: 2026-08-12T09:44:58.347Z
---

# react-jsx

## Description

Support production compiles[^pr] for React 17's [[react-jsx]]  and [[jsxs react factory function]] factory functions.

## Example

```json
// ./src/tsconfig.json
{
    "compilerOptions": {
        "module": "esnext",
        "target": "es2015",
        "jsx": "react-jsx",
        "strict": true
    },
    "include": [
        "./**/*"
    ]
}
```

## Footnotes

[^pr]: https://github.com/microsoft/TypeScript/pull/39199
