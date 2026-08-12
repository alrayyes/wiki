---
publish: true
title: JavaScript RegExp Test Method
created: 2020-11-04T10:17:23
---

test[^test] returns true/false:

```js
let re1 = new RegExp("abc");
let re2 = /abc/;

console.log(re1.test("abc")) // true
console.log(re1.test("acd")) // false
console.log(/abc/.test("abcde")) // true
console.log(/abc/.test("abxde")) // false
```

## Footnotes

[^test]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test
