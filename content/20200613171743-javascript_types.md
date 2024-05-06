---
id: cb93f6ba-527b-4602-b5f4-de0281897800
title: JavaScript Types
---

# Numbers

JavaScript uses 64 bits to store number values

## Fractional numbers

``` javascript
console.log(9.81)
```

## Scientific notation

``` javascript
console.log(2.998e8)
```

## Special Numbers

### Infinity

Infinity and -Infinity represent positive and negative infinities

``` javascript
console.log(Infinity - 1)
console.log(Infinity + 1)
console.log(-Infinity - 1)
console.log(-Infinity + 1)
```

### NaN

Not a number. The returned result if you try to do mathematical nonsense

``` javascript
console.log(0/0)
console.log(Infinity - Infinity)
```

# Boolean

``` javascript
console.log(3 > 2)
console.log(3 < 2)
```

Strings can also be compared

``` javascript
console.log("Aardvark" < "Zoroaster")
```

Uppercase characters are always less than lower case characters, so "Z"
\< "a". Non alphabetic characters are less than alphabetic characters

``` javascript
console.log("Zebra" < "aardvark")
console.log("!" < "aardvark")
console.log("!" < "Zebra")
console.log("3" < "Zebra")
console.log("!" < "3")
```

# Empty values

There are two special empty values, null & undefined that denote the
absence of any meaningful value. They can be used interchangeably and
are an [accident of JavaScripts
design](https://medium.com/@stephenthecurt/a-brief-history-of-null-and-undefined-in-javascript-c283caab662e).

``` javascript
console.log(null == undefined);
```

# Related

-   [JavaScript](20200613170905-javascript)
-   [Arrays](20200826201029-arrays)
-   [Strings](20200922164551-strings)
