---
publish: true
title: JavaScript Types
created: 2020-06-13T17:17:43
---

## Numbers

JavaScript uses 64 bits to store number values

### Fractional numbers

```js
console.log(9.81)
```

### Scientific notation

```js
console.log(2.998e8)
```

### Special Numbers

#### Infinity

Infinity and -Infinity represent positive and negative infinities

```js
console.log(Infinity - 1)
console.log(Infinity + 1)
console.log(-Infinity - 1)
console.log(-Infinity + 1)
```

#### NaN

Not a number. The returned result if you try to do mathematical nonsense

```js
console.log(0/0)
console.log(Infinity - Infinity)
```

## Boolean

```js
console.log(3 > 2)
console.log(3 < 2)
```

Strings can also be compared

```js
console.log("Aardvark" < "Zoroaster")
```

Uppercase characters are always less than lower case characters, so "Z" < "a". Non alphabetic characters are less than alphabetic characters

```js
console.log("Zebra" < "aardvark")
console.log("!" < "aardvark")
console.log("!" < "Zebra")
console.log("3" < "Zebra")
console.log("!" < "3")
```

## Empty values

There are two special empty values, null & undefined that denote the absence of any meaningful value. They can be used interchangeably and are an [accident of JavaScripts design](https://medium.com/@stephenthecurt/a-brief-history-of-null-and-undefined-in-javascript-c283caab662e).

```js
console.log(null == undefined);
```

## Related

- [[JavaScript]]
- [[JavaScript Arrays]]
- [[JavaScript Strings]]
