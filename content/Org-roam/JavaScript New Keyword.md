---
publish: true
title: JavaScript New Keyword
created: 2020-11-13T09:39:10
modified: 2026-08-12T10:26:13.179Z
---

# JavaScript New Keyword

## Description

When you put the keyword ~new~ in front of a function call, the function is treated as a constructor. An [[JavaScript Objects]] with the proper [[JavaScript Prototypes]] is automatically created, bound to ~this~ in the function and returned at the end of the function. This allows you to do OO type stuff.

## Syntax

```js
function Rabbit(type) {
  this.type = type
}
Rabbit.prototype.speak = function(line) {
  console.log(`The ${this.type} rabbit says '${line}'`)
};

let weirdRabbit = new Rabbit("weird")

weirdRabbit.speak("I want carrots!")
```
