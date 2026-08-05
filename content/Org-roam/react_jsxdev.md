---
publish: true
title: react-jsxdev
created: 2020-11-30T08:53:17
modified: 2026-08-05T10:26:50.513Z
---

# react-jsxdev

# Description

Support development compiles for React 17's [react-jsx](react-jsx) and \[jsxs react factory function]\(jsxs react factory function) factory functions. See PR\[fn:pr].

# Example

// ./src/tsconfig.dev.json
{
"extends": "./tsconfig.json",
"compilerOptions": {
"jsx": "react-jsxdev"
}
}

# Footnotes

\[fn:pr]https://github.com/microsoft/TypeScript/pull/39199
