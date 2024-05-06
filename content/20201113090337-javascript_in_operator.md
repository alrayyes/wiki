---
id: 4cd0d42b-3414-4402-95f1-7498fbc52c20
title: JavaScript In Operator
---

# Description

`in`[^1] tells us if indices inside an [array](20200826201029-arrays) or
[object](20200826201605-objects) have no associated element.

# Syntax

``` javascript
const arr = ['a',,'b']
console.log(0 in arr) // true
console.log(1 in arr) // false
console.log(2 in arr) // true
console.log(arr[1]) // undefined
```

``` javascript
const car = { make: "Honda", model: "Accord", year: 1998 };

console.log("make" in car); // true

delete car.make;
if ("make" in car === false) {
  car.make = "Suzuki";
}

console.log(car.make); //Suzuki
```

# Footnotes

[^1]: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in>
