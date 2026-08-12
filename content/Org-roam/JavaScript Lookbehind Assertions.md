---
publish: true
title: JavaScript Lookbehind Assertions
created: 2020-11-09T13:29:44
modified: 2026-08-12T10:31:55.409Z
---

# JavaScript Lookbehind Assertions

## Examples

### Positive lookbehind assertion

Text preceding the current location must match the assertion

```js
const RE_DOLLAR_PREFIX = /(?<=\$)foo/g;
console.log("$foo %foo foo".replace(RE_DOLLAR_PREFIX, "bar")); // '$bar %foo foo'
```

### Negative lookbehind assertion

Text preceding the current location must not match the assertion

```js
const RE_NO_DOLLAR_PREFIX = /(?<!\$)foo/g;
console.log("$foo %foo foo".replace(RE_NO_DOLLAR_PREFIX, "bar")); // '$foo %bar bar'
```
