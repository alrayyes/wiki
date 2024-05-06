---
id: b866160c-ac93-45af-8faf-1fd40f002f77
title: JavaScript Metaprogramming
---

# Introduction

In programming, there are levels:

-   At the *base level* (also called: *application level*), code
    processes user input.
-   At the *meta level*, code processes base level code.

## Examples

An example of this is
[eval](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval)[^1]:

``` javascript
console.log(eval("5 + 2")); // 7
```

``` javascript
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

All [Object.\*
methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#)
can be considered metaprogramming functionality

# Kinds of metaprogramming

Reflective metaprogramming means that a program processes itself.
Kiczales et al[^2]. \[2\] distinguish three kinds of reflective
metaprogramming:

-   **Introspection:** you have read-only access to the structure of a
    program.
-   **Self-modification:** you can change that structure
-   **Intercession:** you can define the semantics of some language
    operations

## Introspection

[Object.keys()](20200826201605-objects.org::*Object.keys) performs
introspection

## self-modification

The following function `moveProperty` moves a property from a source to
a target. It performs self-modification via the bracket operator for
property access, the assignment operator and the delete operator. (In
production code, you’d probably use property descriptors for this task.)

``` javascript
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

## intercession

ECMAScript 5 doesn't support intercession.
[Proxies](20201022094207-javascript_proxies) were created to fill that
gap.

# Footnotes

[^1]: Don't ever use eval. If you think you're a clever clogs that can
    work your away around the obvious security issues, then you
    especially should not use eval.

[^2]: "[The Art of the Metaobject
    Protocol](http://mitpress.mit.edu/books/art-metaobject-protocol)" by
    Gregor Kiczales, Jim des Rivieres and Daniel G. Bobrow. Book, 1991.
