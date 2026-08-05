---
publish: true
title: JavaScript Array Methods
created: 2020-10-09T09:03:31
modified: 2026-08-05T07:58:56.687Z
---

# JavaScript Array Methods

- [ES6](#es6)
  - [Static Array methods](#static-array-methods)
    - [Array.from()](#arrayfrom)
    - [Array.of()](#arrayof)
  - [Array.prototype methods](#arrayprototype-methods)
    - [Array.prototype.fill()](#arrayprototypefill)
    - [Array.prototype.copyWithin()](#arrayprototypecopywithin)
    - [Searching for elements](#searching-for-elements)
      - [Array.prototype.findIndex()](#arrayprototypefindindex)
      - [Array.prototype.find()](#arrayprototypefind)
    - [Iteration](#iteration)
      - [Array.prototype.entries()](#arrayprototypeentries)
      - [Array.prototype.values()](#arrayprototypevalues)
      - [Array.prototype.keys()](#arrayprototypekeys)
- [ES2016](#es2016)
  - [Array.prototype.includes()](#arrayprototypeincludes)

# ES6

## Static Array methods

### Array.from()

```js
const arr2 = Array.from(arguments); // ES6
```

If a value is \[JavaScript Iterables]\(JavaScript Iterables) (as all Array-like DOM data structure are by now), you can also use the [Spread (...)](Spread "...") operator (...) to convert it to an \[JavaScript Arrays]\(JavaScript Arrays):

```js
const arr1 = [...'abc'];
    // ['a', 'b', 'c']
const arr2 = [...new Set().add('a').add('b')];
    // ['a', 'b']
```

### Array.of()

This returns an array of the passed parameters

```js
console.log(Array.of(1, 2, 3, 4)) // [1, 2, 3, 4]
```

## Array.prototype methods

### Array.prototype.fill()

```js
const arr2 = new Array(2).fill(undefined);
    // [undefined, undefined]
```

### Array.prototype.copyWithin()

The method signature is:

```typescript
Array.prototype.copyWithin(target : number,
    start : number, end = this.length) : This
```

It copies the elements whose indices are in the range \[start,end) to index target and subsequent indices. If the two index ranges overlap, care is taken that all source elements are copied before they are overwritten. I am confused as to how this is in any way useful.

```js
const arr = [0,1,2,3];
console.log(arr.copyWithin(2, 0, 2)) // [0, 1, 0, 1]
```

### Searching for elements

#### Array.prototype.findIndex()

```js
console.log([6, -6, 8].findIndex(x => x < 0)) // 1
```

#### Array.prototype.find()

```js
console.log([6, -6, 8].find(x => x < 0)) // -6
```

### Iteration

#### Array.prototype.entries()

```js
console.log(Array.from(['a', 'b'].entries())) // [ [ 0, 'a' ], [ 1, 'b' ] ]
```

#### Array.prototype.values()

```js
console.log(Array.from(['a', 'b'].values())) // ['a', 'b']
```

#### Array.prototype.keys()

```js
console.log(Array.from(['a', 'b'].keys())) // [0, 1]
```

# ES2016

## Array.prototype.includes()

Tells you if array includes a certain element:

```js
console.log(["a", "b", "c"].includes("a")); // true
console.log(["a", "b", "c"].includes("d")); // false
```
