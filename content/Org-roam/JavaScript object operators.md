---
publish: true
title: JavaScript object operators
created: 2020-08-26T20:18:56
---

## Delete operator

The ~delete~ operator deletes a binding (duh)

```js
let anObject = {left: 1, right: 2};
console.log(anObject.left);
delete anObject.left;
console.log(anObject.left);
console.log("left" in anObject);
console.log("right" in anObject);
```

## In operator

The ~in~ operator tells you whether and object has a property with that name

```js
let Object = {
    thisPropertyExists: true
}

console.log("thisPropertyExists" in Object)
console.log("thisPropertyDoesNotExist" in Object)
```
