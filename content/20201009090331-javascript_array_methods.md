---
id: c76b3766-a1ed-43f9-bdb6-4076e6bb5b7a
title: JavaScript Array Methods
---

# ES6

## Static Array methods

### Array.from()

``` javascript
const arr2 = Array.from(arguments); // ES6
```

If a value is [iterable](20201014092625-javascript_iterables) (as all
Array-like DOM data structure are by now), you can also use the
[spread](20201014094144-spread) operator (…) to convert it to an
[Array](20200826201029-arrays):

``` javascript
const arr1 = [...'abc'];
    // ['a', 'b', 'c']
const arr2 = [...new Set().add('a').add('b')];
    // ['a', 'b']
```

### Array.of()

This returns an array of the passed parameters

``` javascript
console.log(Array.of(1, 2, 3, 4)) // [1, 2, 3, 4]
```

## Array.prototype methods

### Array.prototype.fill()

``` javascript
const arr2 = new Array(2).fill(undefined);
    // [undefined, undefined]
```

### Array.prototype.copyWithin()

The method signature is:

``` typescript
Array.prototype.copyWithin(target : number,
    start : number, end = this.length) : This
```

It copies the elements whose indices are in the range \[start,end) to
index target and subsequent indices. If the two index ranges overlap,
care is taken that all source elements are copied before they are
overwritten. I am confused as to how this is in any way useful.

``` javascript
const arr = [0,1,2,3];
console.log(arr.copyWithin(2, 0, 2)) // [0, 1, 0, 1]
```

### Searching for elements

1.  Array.prototype.findIndex()

    ``` javascript
    console.log([6, -6, 8].findIndex(x => x < 0)) // 1
    ```

2.  Array.prototype.find()

    ``` javascript
    console.log([6, -6, 8].find(x => x < 0)) // -6
    ```

### Iteration

1.  Array.prototype.entries()

    ``` javascript
    console.log(Array.from(['a', 'b'].entries())) // [ [ 0, 'a' ], [ 1, 'b' ] ]
    ```

2.  Array.prototype.values()

    ``` javascript
    console.log(Array.from(['a', 'b'].values())) // ['a', 'b']
    ```

3.  Array.prototype.keys()

    ``` javascript
    console.log(Array.from(['a', 'b'].keys())) // [0, 1]
    ```

# ES2016

## Array.prototype.includes()

Tells you if array includes a certain element:

``` javascript
console.log(["a", "b", "c"].includes("a")); // true
console.log(["a", "b", "c"].includes("d")); // false
```
