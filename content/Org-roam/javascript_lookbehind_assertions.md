---
publish: true
title: JavaScript Lookbehind Assertions
created: 2020-11-09T13:29:44
modified: 2026-08-05T07:58:56.690Z
---

# JavaScript Lookbehind Assertions

- [Examples](#examples)
  - [Positive lookbehind assertion](#positive-lookbehind-assertion)
  - [Negative lookbehind assertion](#negative-lookbehind-assertion)

# Examples

## Positive lookbehind assertion

Text preceding the current location must match the assertion
const RE\_DOLLAR\_PREFIX = /(?<=\$)foo/g;
console.log("$foo %foo foo".replace(RE_DOLLAR_PREFIX, "bar")); // '$bar %foo foo'

## Negative lookbehind assertion

Text preceding the current location must not match the assertion
const RE\_NO\_DOLLAR\_PREFIX = /(?\<!\$)foo/g;
console.log("$foo %foo foo".replace(RE_NO_DOLLAR_PREFIX, "bar")); // '$foo %bar bar'
