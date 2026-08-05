---
publish: true
title: JavaScript Prototypes
created: 2020-11-13T09:14:24
modified: 2026-08-05T10:26:50.506Z
---

# JavaScript Prototypes

- [Description](#description)
- [Syntax](#syntax)
- [Object.prototype](#objectprototype)
- [Footnotes](#footnotes)

# Description

A prototype can be seen as an \[JavaScript Objects]\(JavaScript Objects) another object extends.

# Syntax

```js
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

Most objects in JavaScript eventually extend ~Object.prototype~ through parent prototype objects or directly, which provides a bunch of default methods\[fn:defaultmethods].

```js
console.log(Object.getPrototypeOf({}) == Object.prototype); // true
console.log(Object.getPrototypeOf(Object.prototype)); // null
```

# Footnotes

\[fn:defaultmethods]https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object
