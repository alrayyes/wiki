---
publish: true
title: JavaScript Instanceof Operator
created: 2020-11-13T09:42:46
modified: 2026-08-12T09:44:58.332Z
---

# JavaScript Instanceof Operator

## Description

Sometimes you want to know whether an [[JavaScript Objects]] was derived from a specific [[JavaScript Class Notation]]. To do this one can use the ~instanceof~ [[JavaScript Operators]].

## Syntax

```js
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
