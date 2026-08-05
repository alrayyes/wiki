---
publish: true
title: JavaScript Class Notation
created: 2020-10-08T09:03:16
modified: 2026-08-05T10:26:50.496Z
---

# JavaScript Class Notation

- [Introduction](#introduction)
- [Example](#example)

# Introduction

By convention, the names of constructors are capitalized so that they can easily be distinguished from other functions. Thanks to \[\[https://ecma-international.org/ecma-262/6.0/]\[ECMAScript 2015]] above can be achieved with a saner notation:

# Example

```js
class Rabbit {
  constructor(type) {
    this.type = type;
  }
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
}

let killerRabbit = new Rabbit("killer");
let blackRabbit = new Rabbit("black");

killerRabbit.speak("I want blood!");
blackRabbit.speak("For some reason I appreciate Tyler Perry movies");
```

If one _must_ one can also use ~class~ in expressions:

```js
let object = new class { getWord() { return "hello"; } };
console.log(object.getWord());
```
