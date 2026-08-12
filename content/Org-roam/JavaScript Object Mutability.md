---
publish: true
title: JavaScript Object Mutability
created: 2020-08-26T20:17:37
---

# JavaScript Object Mutability

## Description

With objects, there is a difference between having two references to the same object and having two different objects that contain the same properties.

## Examples

```js
let object1 = {value: 10};
let object2 = object1;
let object3 = {value: 10};

console.log(object1 == object2); // true
console.log(object1 == object3); // false

object1.value = 15;
console.log(object2.value); // 15
console.log(object3.value); // 10
```

`const` objects can have their values changed

```js
const score = { visitors: 0, home: 1 };
score.visitors = 23;

console.log(score); // { visitors: 23, home: 1 }
```
