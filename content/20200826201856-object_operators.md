---
id: 7b46ba87-7328-479c-8d79-badb24ed7b19
title: JavaScript object operators
---

# Delete operator

The `delete` operator deletes a binding (duh)

``` javascript
let anObject = {left: 1, right: 2};
console.log(anObject.left);
delete anObject.left;
console.log(anObject.left);
console.log("left" in anObject);
console.log("right" in anObject);
```

# In operator

The `in` operator tells you whether and object has a property with that
name

``` javascript
let Object = {
    thisPropertyExists: true
}

console.log("thisPropertyExists" in Object)
console.log("thisPropertyDoesNotExist" in Object)
```
