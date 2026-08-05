---
publish: true
title: JavaScript Lookahead Assertions
created: 2020-11-09T13:24:57
modified: 2026-08-05T07:58:56.690Z
---

# JavaScript Lookahead Assertions

- [Examples](#examples)
  - [Positive lookahead assertion](#positive-lookahead-assertion)
  - [Negative lookahead assertion](#negative-lookahead-assertion)

# Examples

## Positive lookahead assertion

Text after the current location must match the assertion
const RE\_AS\_BS = /aa(?=bb)/;
const match1 = RE\_AS\_BS.exec("aabb");
console.log(match1\[0]); // 'aa'

## Negative lookahead assertion

Text after the current location must not match the assertion
const RE\_AS\_NO\_BS = /aa(?!bb)/;

console.log(RE\_AS\_NO\_BS.test("aabb")); // false
console.log(RE\_AS\_NO\_BS.test("aab")); // true
console.log(RE\_AS\_NO\_BS.test("aac")); // true
