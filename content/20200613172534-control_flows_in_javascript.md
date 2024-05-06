---
id: adffc782-d978-49f3-9367-33e77b05af8a
title: Control flows in JavaScript
---

# ES6

## for-of

``` javascript
const arr = ['a', 'b', 'c'];
for (const elem of arr) {
    console.log(elem);
}
```

``` javascript
const arr = ['a', 'b', 'c'];
for (const [index, elem] of arr.entries()) {
    console.log(index+'. '+elem);
}
```

# if statement

``` javascript
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

# while statement

``` javascript
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

# for statement

``` javascript
for(let k = 0; k <= 5; k++) {
    console.log("For loop k " + k)
}
```

# switch statement

``` javascript
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

# Breaking out of a loop

``` javascript
for (let current = 20; ; current = current + 1) {
  if (current % 7 == 0) {
    console.log(current);
    break;
  }
}
```

# Comments

``` javascript
// This is a one line comment
let i = 0

/**
 This is a multi line comment
 Here is the second line
*/
let j = 0
```
