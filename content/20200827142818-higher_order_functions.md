---
id: 513ff88e-d0c9-41d1-8416-57a4aff100c7
title: JavaScript higher-order functions
---

# Examples

Functions that operate on other functions, either by taking them as
arguments or by returning them, are called higher-order functions. They
allow us to abstract over actions as well as values. There are several
types, here are some examples.

## Functions that create new functions

``` javascript
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
```

## Functions that change other functions

``` javascript
function noisy(f) {
  return (...args) => {
    console.log("calling with", args);
    let result = f(...args);
    console.log("called with", args, ", returned", result);
    return result;
  };
}
noisy(Math.min)(3, 2, 1);
```

## Functions that provide new types of flow control

``` javascript
function unless(test, then) {
  if (!test) then();
}

repeat(3, n => {
  unless(n % 2 == 1, () => {
    console.log(n, "is even");
  });
});
```

## ES6

### Funciton properties

1.  name

    The `name` property contains the function's name:

    ``` javascript
    function foo() {};
    console.log(foo.name); // foo

    let func1 = function () {};
    console.log(func1.name); // func1

    let func4;
    func4 = function () {};
    console.log(func4.name); // func4
    ```

    1.  Default values

        ``` javascript
        let [func1 = function () {}] = [];
        console.log(func1.name); // func1

        let { f2: func2 = function () {} } = {};
        console.log(func2.name); // func2

        function g(func3 = function () {}) {
            return func3.name;
        }
        console.log(g()); // func3
        ```
