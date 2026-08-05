---
publish: true
title: Array.prototype.flatMap()
created: 2020-11-13T11:20:58
modified: 2026-08-05T10:26:50.494Z
---

# Array.prototype.flatMap()

# Description

Is the same as calling \[JavaScript Maps]\(JavaScript Maps) and then flattening the result. Ie:

arr.map(func).flat(1)

# Type Signature

.flatMap<U>(
callback: (value: T, index: number, array: T\[]) => U|Array<U>,
thisValue?: any
): U\[]

# Syntax

console.log(\["a", "b", "c"].flatMap((x) => x)); // \[ 'a', 'b', 'c' ]
console.log(\["a", "b", "c"].flatMap((x) => \[x])); // \[ 'a', 'b', 'c' ]
console.log(\["a", "b", "c"].flatMap((x) => [x](x))); // \[ \[ 'a' ], \[ 'b' ], \[ 'c' ] ]
console.log(\["a", "b", "c"].flatMap((x, i) => new Array(i + 1).fill(x))); // \[ 'a', 'b', 'b', 'c', 'c', 'c' ]
