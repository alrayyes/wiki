---
publish: true
title: Spread (...)
created: 2020-10-14T09:41:44
---

## Examples

Math.max() returns the numerically greatest of its arguments. It works for an arbitrary number of arguments, but not for Arrays.

```js
console.log(Math.max(...[-1, 5, 11, 3]))
```

```js
const arr1 = ['a', 'b'];
const arr2 = ['c', 'd'];

arr1.push(...arr2); // arr1 is now ['a', 'b', 'c', 'd']
```

```js
const arr1 = ['a', 'b'];
const arr2 = ['c'];
const arr3 = ['d', 'e'];

console.log([...arr1, ...arr2, ...arr3]); // [ 'a', 'b', 'c', 'd', 'e' ]
```
