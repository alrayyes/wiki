---
publish: true
title: JavaScript In Operator
created: 2020-11-13T09:03:37
modified: 2026-08-05T07:58:56.689Z
---

# JavaScript In Operator

- [Description](#description)
- [Syntax](#syntax)
- [Footnotes](#footnotes)

# Description

\~in~\[fn:in] tells us if indices inside an \[JavaScript Arrays]\(JavaScript Arrays) or \[JavaScript Objects]\(JavaScript Objects) have no associated element.

# Syntax

```js
const arr = ['a',,'b']
console.log(0 in arr) // true
console.log(1 in arr) // false
console.log(2 in arr) // true
console.log(arr[1]) // undefined
```

const car = { make: "Honda", model: "Accord", year: 1998 };

console.log("make" in car); // true

delete car.make;
if ("make" in car === false) {
car.make = "Suzuki";
}

console.log(car.make); //Suzuki

# Footnotes

\[fn:in]https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in
