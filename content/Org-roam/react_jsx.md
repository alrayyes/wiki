---
publish: true
title: react-jsx
created: 2020-11-30T08:52:53
modified: 2026-08-05T07:58:56.705Z
---

# react-jsx

# Description

Support production compiles\[fn:pr] for React 17's [react-jsx](react-jsx)  and \[jsxs react factory function]\(jsxs react factory function) factory functions.

# Example

// ./src/tsconfig.json
{
"compilerOptions": {
"module": "esnext",
"target": "es2015",
"jsx": "react-jsx",
"strict": true
},
"include": \[
"./\*\*/\*"
]
}

# Footnotes

\[fn:pr]https://github.com/microsoft/TypeScript/pull/39199
