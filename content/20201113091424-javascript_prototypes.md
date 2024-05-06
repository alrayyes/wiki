---
id: fd03be0e-a4c0-421f-9dd7-1bddc9dece65
title: JavaScript Prototypes
---

# Description

A prototype can be seen as an [object](20200826201605-objects) another
object extends.

# Syntax

``` javascript
let protoRabbit = {
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`); // : The killer rabbit says 'SKREEEE!'
  },
};
let killerRabbit = Object.create(protoRabbit);
killerRabbit.type = "killer";
killerRabbit.speak("SKREEEE!");
```

# Object.prototype

Most objects in JavaScript eventually extend `Object.prototype` through
parent prototype objects or directly, which provides a bunch of default
methods[^1].

``` javascript
console.log(Object.getPrototypeOf({}) == Object.prototype); // true
console.log(Object.getPrototypeOf(Object.prototype)); // null
```

# Footnotes

[^1]: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object>
