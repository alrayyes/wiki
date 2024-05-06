---
id: c0bfe9b7-f543-4f89-9661-94d8bb406ff7
title: JavaScript BigInt
---

# Description

`BigInt` can handle numbers larger than 9~007199254740991~.

# Syntax

``` javascript
const previouslyMaxSafeInteger = 9007199254740991n;

const alsoHuge = BigInt(9007199254740991);
// ↪ 9007199254740991n

const hugeString = BigInt("9007199254740991");
// ↪ 9007199254740991n

const hugeHex = BigInt("0x1fffffffffffff");
// ↪ 9007199254740991n

const hugeBin = BigInt(
  "0b11111111111111111111111111111111111111111111111111111"
);
// ↪ 9007199254740991n
```
