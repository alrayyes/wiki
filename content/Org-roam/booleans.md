---
publish: true
title: JavaScript Booleans
created: 2020-09-22T16:47:27
modified: 2026-08-05T10:26:50.495Z
---

# JavaScript Booleans

# Syntax

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

There are two special empty values, null & undefined that denote the absence of any meaningful value. They can be used interchangeably and are an \[\[https://medium.com/@stephenthecurt/a-brief-history-of-null-and-undefined-in-javascript-c283caab662e]\[accident of JavaScripts design]].

```js
console.log(null == undefined);
```
