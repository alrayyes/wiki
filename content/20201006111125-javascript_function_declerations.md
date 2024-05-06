---
id: 0e8d8e26-e36d-48b6-a333-9c0fbd07b7b0
title: JavaScript function declarations
---

``` javascript
const square = function(x) {
    return x * x;
}

console.log(square(12))
```

``` javascript
const makeNoise = function() {
    console.log("Pling!")
}

makeNoise()
```

``` javascript
const power = function(base, exponent) {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};

console.log(power(2, 10))
```
