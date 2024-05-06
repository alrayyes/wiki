---
id: eff92c39-8459-4f55-a34b-d924eb603056
title: JavaScript RegExp Test Method
---

test[^1] returns true/false:

``` javascript
let re1 = new RegExp("abc");
let re2 = /abc/;

console.log(re1.test("abc")) // true
console.log(re1.test("acd")) // false
console.log(/abc/.test("abcde")) // true
console.log(/abc/.test("abxde")) // false
```

# Footnotes

[^1]: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test>
