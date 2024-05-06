---
id: d1549dd2-a5fc-4583-a186-5de02ca40d33
title: JavaScript Lookbehind Assertions
---

# Examples

## Positive lookbehind assertion

Text preceding the current location must match the assertion

``` javascript
const RE_DOLLAR_PREFIX = /(?<=\$)foo/g;
console.log("$foo %foo foo".replace(RE_DOLLAR_PREFIX, "bar")); // '$bar %foo foo'
```

## Negative lookbehind assertion

Text preceding the current location must not match the assertion

``` javascript
const RE_NO_DOLLAR_PREFIX = /(?<!\$)foo/g;
console.log("$foo %foo foo".replace(RE_NO_DOLLAR_PREFIX, "bar")); // '$foo %bar bar'
```
