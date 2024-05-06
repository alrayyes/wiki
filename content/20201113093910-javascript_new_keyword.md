---
id: 32b0031a-0830-4e8c-a39c-3bf6d8791f84
title: JavaScript New Keyword
---

# Description

When you put the keyword `new` in front of a function call, the function
is treated as a constructor. An [object](20200826201605-objects) with
the proper [prototype](20201113091424-javascript_prototypes) is
automatically created, bound to `this` in the function and returned at
the end of the function. This allows you to do OO type stuff.

# Syntax

``` javascript
function Rabbit(type) {
  this.type = type
}
Rabbit.prototype.speak = function(line) {
  console.log(`The ${this.type} rabbit says '${line}'`)
};

let weirdRabbit = new Rabbit("weird")

weirdRabbit.speak("I want carrots!")
```
