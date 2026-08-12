---
publish: true
title: JavaScript In Operator
created: 2020-11-13T09:03:37
modified: 2026-08-12T10:31:55.408Z
---

# JavaScript In Operator

## Description

\~in~[^in] tells us if indices inside an [[JavaScript Arrays]] or [[JavaScript Objects]] have no associated element.

## Syntax

```js
const arr = ['a',,'b']
console.log(0 in arr) // true
console.log(1 in arr) // false
console.log(2 in arr) // true
console.log(arr[1]) // undefined
```

```js
const car = { make: "Honda", model: "Accord", year: 1998 };

console.log("make" in car); // true

delete car.make;
if ("make" in car === false) {
  car.make = "Suzuki";
}

console.log(car.make); //Suzuki
```

## Footnotes

[^in]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in
