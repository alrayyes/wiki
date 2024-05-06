---
id: eb8253f8-f376-4b73-9098-35da64a5a6e7
title: Destructuring Default Values
---

# Basic syntax

``` javascript
const [x=3, y] = []
console.log(x, y) // 3 undefined
```

# Computed on demand

Default values are computed when they are needed:

``` javascript
function tralala() {
    return "tralala string"
}

const {computed=tralala()} = {}
console.log(computed) // tralala string
```

# Refer to other variables

Default value an refer to other
[variables](20200613170532-variable_types_in_javascript) in the same
pattern:

``` javascript
const [x=3, y=x] = [];     // x=3; y=3
const [i=3, j=x] = [7];    // i=7; j=7
const [k=3, l=x] = [7, 2]; // k=7; l=2
```
