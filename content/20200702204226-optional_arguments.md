---
id: 6e1019ae-983e-42c6-90cf-daa6aebb86ea
title: Optional arguments in JavaScript functions
---

JavaScript is extremely broad-minded about the number of arguments you
pass to a function. If you pass too many, the extra ones are ignored. If
you pass too few, the missing parameters get assigned the value
`undefined`.

``` javascript
function square(x) { return x * x; }
console.log(square(4, true, "hedgehog"));
```

``` javascript
function minus(a, b) {
  if (b === undefined) return -a;
  else return a - b;
}

console.log(minus(10));
console.log(minus(10, 5));
```

Function parameters can also be given default values

``` javascript
function power(base, exponent = 2) {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
}

console.log(power(4));
console.log(power(2, 6));
```
