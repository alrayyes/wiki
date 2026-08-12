---
publish: true
title: Destructuring Default Values
created: 2020-11-03T11:31:24
modified: 2026-08-12T10:26:13.164Z
---

# Destructuring Default Values

## Basic syntax

```js
const [x=3, y] = []
console.log(x, y) // 3 undefined
```

## Computed on demand

Default values are computed when they are needed:

```js
function tralala() {
    return "tralala string"
}

const {computed=tralala()} = {}
console.log(computed) // tralala string
```

## Refer to other variables

Default value an refer to other [[JavaScript Variables]] in the same pattern:

```js
const [x=3, y=x] = [];     // x=3; y=3
const [i=3, j=x] = [7];    // i=7; j=7
const [k=3, l=x] = [7, 2]; // k=7; l=2
```
