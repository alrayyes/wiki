---
id: 54c58f54-526f-4838-92c5-1a70d6b17a3c
title: JavaScript Instanceof Operator
---

# Description

Sometimes you want to know whether an [object](20200826201605-objects)
was derived from a specific [class](20201008090316-class_notation). To
do this one can use the `instanceof`
[operator](20200613170705-operators_in_javascript).

# Syntax

``` javascript
class Parent {
  constructor(name, parentChild = "Parent") {
    this.parentChild = parentChild;
    this.name = name;
  }

  speak(line) {
    console.log(`${this.parentChild} ${this.name} says '${line}'`);
  }
}

class Child extends Parent {
  constructor(name) {
    super(name, "Child");
  }
}

let parent = new Parent("Father");
let child = new Child("Gregory");

console.log(parent instanceof Parent); // true
console.log(parent instanceof Child); // false
console.log(child instanceof Parent); // true
console.log(child instanceof Child); // true
```
