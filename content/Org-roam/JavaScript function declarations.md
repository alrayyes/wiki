---
publish: true
title: JavaScript function declarations
created: 2020-10-06T11:11:25
---

```js
const square = function(x) {
    return x * x;
}

console.log(square(12))
```

```js
const makeNoise = function() {
    console.log("Pling!")
}

makeNoise()
```

```js
const power = function(base, exponent) {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};

console.log(power(2, 10))
```
