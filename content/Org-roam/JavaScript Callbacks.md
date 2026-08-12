---
publish: true
title: JavaScript Callbacks
created: 2020-09-11T15:04:51
modified: 2026-08-12T10:31:55.406Z
---

# JavaScript Callbacks

## Examples

### setTimeout

```js
setTimeout(() => {  console.log("This will echo after 2 seconds!"); }, 2000);
```

## ES6

### Best practices

#### Prefer arrow functions as callbacks

As callbacks, [[JavaScript arrow functions]] have two advantages over traditional functions:

- \~this~ is lexical and therefore safer to use.
- Their syntax is more compact. That matters especially in functional programming, where there are many higher-order functions and methods (functions and methods whose parameters are functions).
