---
id: 3ab00edf-6c63-4db2-b32e-d18f8d683329
title: JavaScript Lookahead Assertions
---

# Examples

## Positive lookahead assertion

Text after the current location must match the assertion

``` javascript
const RE_AS_BS = /aa(?=bb)/;
const match1 = RE_AS_BS.exec("aabb");
console.log(match1[0]); // 'aa'
```

## Negative lookahead assertion

Text after the current location must not match the assertion

``` javascript
const RE_AS_NO_BS = /aa(?!bb)/;

console.log(RE_AS_NO_BS.test("aabb")); // false
console.log(RE_AS_NO_BS.test("aab")); // true
console.log(RE_AS_NO_BS.test("aac")); // true
```
