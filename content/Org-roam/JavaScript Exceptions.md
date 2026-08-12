---
publish: true
title: JavaScript Exceptions
created: 2020-11-11T09:29:05
---

# JavaScript Exceptions

## Introduction

[[JavaScript]] supports exceptions.

## Syntax

```js
function promptDirection(question) {
  let result = prompt(question);
  if (result.toLowerCase() == "left") return "L";
  if (result.toLowerCase() == "right") return "R";
  throw new Error("Invalid direction: " + result);
}

function look() {
  if (promptDirection("Which way?") == "L") {
    return "a house";
  } else {
    return "two angry bears";
  }
}

try {
  console.log("You see", look());
} catch (error) {
  console.log("Something went wrong: " + error);
}
```

## See also

- [[JavaScript Error Sub Types]]
- [[JavaScript Custom Error Types]]
- [[JavaScript Exceptions Finally]]
- [[JavaScript Error Handling]]
- [[JavaScript]]
- [[JavaScript Catch Binding]]
