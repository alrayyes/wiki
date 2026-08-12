---
publish: true
title: JavaScript Lookahead Assertions
created: 2020-11-09T13:24:57
modified: 2026-08-12T10:26:13.179Z
---

# JavaScript Lookahead Assertions

## Examples

### Positive lookahead assertion

Text after the current location must match the assertion

```js
const RE_AS_BS = /aa(?=bb)/;
const match1 = RE_AS_BS.exec("aabb");
console.log(match1[0]); // 'aa'
```

### Negative lookahead assertion

Text after the current location must not match the assertion

```js
const RE_AS_NO_BS = /aa(?!bb)/;

console.log(RE_AS_NO_BS.test("aabb")); // false
console.log(RE_AS_NO_BS.test("aab")); // true
console.log(RE_AS_NO_BS.test("aac")); // true
```
