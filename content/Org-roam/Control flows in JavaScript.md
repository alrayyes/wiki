---
publish: true
title: Control flows in JavaScript
created: 2020-06-13T17:25:34
modified: 2026-08-12T10:31:55.392Z
---

# Control flows in JavaScript

## ES6

### for-of

```js
const arr = ['a', 'b', 'c'];
for (const elem of arr) {
    console.log(elem);
}
```

```js
const arr = ['a', 'b', 'c'];
for (const [index, elem] of arr.entries()) {
    console.log(index+'. '+elem);
}
```

## if statement

```js
if(true === true) {
    console.log("True is true")
}

if (true === false) {
    console.log("True is false")
}
else {
    console.log("True is not false")
}
```

## while statement

```js
let i = 0
while (i <= 5) {
    console.log("Loop " + i)
    i++
}

let j = 0
do {
    j++
} while (j <= 5)
console.log("Do while j value is " + j)
```

## for statement

```js
for(let k = 0; k <= 5; k++) {
    console.log("For loop k " + k)
}
```

## switch statement

```js
switch ("rainy") {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}

switch ("sunny") {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}

switch ("wild card") {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}
```

## Breaking out of a loop

```js
for (let current = 20; ; current = current + 1) {
  if (current % 7 == 0) {
    console.log(current);
    break;
  }
}
```

## Comments

```js
// This is a one line comment
let i = 0

/**
 This is a multi line comment
 Here is the second line
,*/
let j = 0
```
