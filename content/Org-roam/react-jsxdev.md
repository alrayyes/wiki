---
publish: true
title: react-jsxdev
created: 2020-11-30T08:53:17
modified: 2026-08-12T10:31:55.424Z
---

# react-jsxdev

## Description

Support development compiles for React 17's [[react-jsx]] and [[jsxs react factory function]] factory functions. See PR[^pr].

## Example

```json
// ./src/tsconfig.dev.json
{
    "extends": "./tsconfig.json",
    "compilerOptions": {
        "jsx": "react-jsxdev"
    }
}
```

## Footnotes

[^pr]: https://github.com/microsoft/TypeScript/pull/39199
