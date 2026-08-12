---
publish: true
title: JavaScript Variables
created: 2020-06-13T17:05:32
modified: 2026-08-12T10:31:55.415Z
---

# JavaScript Variables

## Types

### Numbers

JavaScript uses 64 bits to store number values

#### Fractional numbers

```js
console.log(9.81)
```

#### Scientific notation

```js
console.log(2.998e8)
```

#### Special Numbers

##### Infinity

Infinity and -Infinity represent positive and negative infinities

```js
console.log(Infinity - 1)
console.log(Infinity + 1)
console.log(-Infinity - 1)
console.log(-Infinity + 1)
```

##### NaN

Not a number. The returned result if you try to do mathematical nonsense

```js
console.log(0/0)
console.log(Infinity - Infinity)
```

### Strings

Following are acceptable strings

```js
console.log(`Down on the sea`)
console.log("Lie on the ocean")
console.log('Float on the ocean')
```

Backslash escapes characters

```js
console.log("This is the first line\nAnd this is the second")
console.log("A newline character is written like \"\\n\".")
```

Backtick quoted strings ([template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)) can span lines and also embed other values. \${} in a template literal will be computed and converted to a string

```js
console.log(`This is a
backtick quotes string`)
console.log(`half of 100 is ${100 / 2}`)
```

### Boolean

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

### Empty values

There are two special empty values, null & undefined that denote the absence of any meaningful value. They can be used interchangeably and are an [accident of JavaScripts design](https://medium.com/@stephenthecurt/a-brief-history-of-null-and-undefined-in-javascript-c283caab662e).

```js
console.log(null == undefined);
```

## ES6

### Symbols

They are tokens that serve as unique IDs. You create symbols via the factory function Symbol() (which is loosely similar to String returning strings if called as a function):

```js
const symbol1 = Symbol();
```

#### Add a description

```js
const tralala = Symbol('tralala')
console.log(tralala) // Symbol(tralala)
```

#### Convert to string

```js
const tralala = Symbol('tralala')
console.log(String(tralala)) // `Symbol(tralala)`
```

#### Every Symbol is unique

```js
console.log(Symbol() === Symbol()) // false
```

#### Property keys

```js
const KEY = Symbol();
const obj = {};

obj[KEY] = 123;
console.log(obj[KEY]); // 123
```

```js
const FOO = Symbol();
const obj = {
    [FOO]() {
        return 'bar';
    }
};
console.log(obj[FOO]()); // bar
```
