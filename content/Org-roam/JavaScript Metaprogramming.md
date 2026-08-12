---
publish: true
title: JavaScript Metaprogramming
created: 2020-10-22T09:54:38
---

## Introduction

In programming, there are levels:

- At the /base level/ (also called: /application level/), code processes user input.
- At the /meta level/, code processes base level code.

### Examples

An example of this is [eval](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval)[^eval]:

```js
console.log(eval("5 + 2")); // 7
```

```js
const obj = {
  hello() {
    console.log("Hello!");
  },
};

// Meta level
for (const key of Object.keys(obj)) {
  console.log(key);
}
```

All [Object.\* methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#) can be considered metaprogramming functionality

## Kinds of metaprogramming

Reflective metaprogramming means that a program processes itself. Kiczales et al[^metaprogramming]. \[2] distinguish three kinds of reflective metaprogramming:

- _Introspection:_ you have read-only access to the structure of a program.
- _Self-modification:_ you can change that structure
- _Intercession:_ you can define the semantics of some language operations

### Introspection

[Object.keys()](file:20200826201605-objects.org::*Object.keys) performs introspection

### self-modification

The following function ~moveProperty~ moves a property from a source to a target. It performs self-modification via the bracket operator for property access, the assignment operator and the delete operator. (In production code, you’d probably use property descriptors for this task.)

```js
function moveProperty(source, propertyName, target) {
  target[propertyName] = source[propertyName];
  delete source[propertyName];
}

const obj1 = { prop: "abc" };
const obj2 = {};
moveProperty(obj1, "prop", obj2);

console.log(obj1); // {}
console.log(obj2); // { prop: 'abc' }
```

### intercession

ECMAScript 5 doesn't support intercession. [[JavaScript Proxies]] were created to fill that gap.

## Footnotes

[^metaprogramming]: "[The Art of the Metaobject Protocol](http://mitpress.mit.edu/books/art-metaobject-protocol)"  by Gregor Kiczales, Jim des Rivieres and Daniel G. Bobrow. Book, 1991.
Don't ever use eval. If you think you're a clever clogs that can work your away around the obvious security issues, then you especially should not use eval.
