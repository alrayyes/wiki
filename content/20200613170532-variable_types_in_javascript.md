---
id: 8af0e4ee-b090-4903-9ab7-020a4b7328ef
title: JavaScript Variables
---

# Types

## Numbers

JavaScript uses 64 bits to store number values

### Fractional numbers

``` javascript
console.log(9.81)
```

### Scientific notation

``` javascript
console.log(2.998e8)
```

### Special Numbers

1.  Infinity

    Infinity and -Infinity represent positive and negative infinities

    ``` javascript
    console.log(Infinity - 1)
    console.log(Infinity + 1)
    console.log(-Infinity - 1)
    console.log(-Infinity + 1)
    ```

2.  NaN

    Not a number. The returned result if you try to do mathematical
    nonsense

    ``` javascript
    console.log(0/0)
    console.log(Infinity - Infinity)
    ```

## Strings

Following are acceptable strings

``` javascript
console.log(`Down on the sea`)
console.log("Lie on the ocean")
console.log('Float on the ocean')
```

Backslash escapes characters

``` javascript
console.log("This is the first line\nAnd this is the second")
console.log("A newline character is written like \"\\n\".")
```

Backtick quoted strings ([template
literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals))
can span lines and also embed other values. \${} in a template literal
will be computed and converted to a string

``` javascript
console.log(`This is a
backtick quotes string`)
console.log(`half of 100 is ${100 / 2}`)
```

## Boolean

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

## Empty values

There are two special empty values, null & undefined that denote the
absence of any meaningful value. They can be used interchangeably and
are an [accident of JavaScripts
design](https://medium.com/@stephenthecurt/a-brief-history-of-null-and-undefined-in-javascript-c283caab662e).

``` javascript
console.log(null == undefined);
```

# ES6

## Symbols

They are tokens that serve as unique IDs. You create symbols via the
factory function Symbol() (which is loosely similar to String returning
strings if called as a function):

``` javascript
const symbol1 = Symbol();
```

### Add a description

``` javascript
const tralala = Symbol('tralala')
console.log(tralala) // Symbol(tralala)
```

### Convert to string

``` javascript
const tralala = Symbol('tralala')
console.log(String(tralala)) // `Symbol(tralala)`
```

### Every Symbol is unique

``` javascript
console.log(Symbol() === Symbol()) // false
```

### Property keys

``` javascript
const KEY = Symbol();
const obj = {};

obj[KEY] = 123;
console.log(obj[KEY]); // 123
```

``` javascript
const FOO = Symbol();
const obj = {
    [FOO]() {
        return 'bar';
    }
};
console.log(obj[FOO]()); // bar
```
