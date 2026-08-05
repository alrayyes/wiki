---
publish: true
title: JavaScript BigInt
created: 2020-11-16T16:58:19
modified: 2026-08-05T07:58:56.688Z
---

# JavaScript BigInt

# Description

\~BigInt~ can handle numbers larger than 9\_007\_199\_254\_740\_991.

# Syntax

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
