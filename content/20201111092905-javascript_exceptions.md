---
id: 44e4d5c4-ea16-4417-a8e8-5036d3fdd370
title: JavaScript Exceptions
---

# Introduction

[JavaScript](20200613170905-javascript) supports exceptions.

# Syntax

``` javascript
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

# See also

-   [Error Sub Types](20201111093101-javascript_error_sub_types)
-   [Custom Error Types](20201111093651-javascript_custom_error_types)
-   [Finally](20201111094033-javascript_exceptions_finally)
-   [JavaScript Error Handling](20200901105237-error_handling)
-   [JavaScript](20200613170905-javascript)
-   [JavaScript Catch Binding](20201116154444-javascript_catch_binding)
