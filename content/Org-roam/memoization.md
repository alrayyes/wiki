---
publish: true
title: memoization
created: 2020-11-26T10:19:55
modified: 2026-08-05T07:58:56.697Z
---

# memoization

# Origin

Latin for "mindful remembering"

# Description

Cache the return value of a function

# Example

const memo = {}

function fib(n) {
if(memo\[n]) {
return memo\[n]
}
if(n <= 1) {
return 1
}

```
return memo[n] = fib(n -1) + fib(n - 2)
```

}

fib(5)
console.log(memo) // { '2': 2, '3': 3, '4': 5, '5': 8 }
