---
id: 40bc3b60-ab05-4ff6-a258-f5cb38322c77
title: Bindings and scopes in JavaScript
---

# Bindings

-   For bindings defined outside of any function or block, the scope is
    the whole program. We call these `global` bindings
-   Bindings created for function parameters or declared inside a
    function can only be referenced in that function. These are known as
    `local` bindings. New instances of these `local` bindings are
    created every time the function is called
-   Bindings declared with `let` and `const` are local to the block that
    they are declared in
-   In pre-2015 JavaScript, only functions created new scopes. So
    old-style bindings created with `var` are visible throughout the
    whole function that they appear in. If not declared in a function
    then scope is `global`

``` javascript
let x = 10
if (true) {
    let y = 20
    var z = 30
    console.log(x + y + z)
}

// y is not accessable here
console.log(x + z)
```

``` javascript
const halve = function(n) {
    return n / 2
}

let n = 10

console.log(halve(100))
console.log(n)
```

# Nested scope

``` javascript
const hummus = function(factor) {
  const ingredient = function(amount, unit, name) {
    let ingredientAmount = amount * factor;
    if (ingredientAmount > 1) {
      unit += "s";
    }
    console.log(`${ingredientAmount} ${unit} ${name}`);
  };
  ingredient(1, "can", "chickpeas");
  ingredient(0.25, "cup", "tahini");
  ingredient(0.25, "cup", "lemon juice");
  ingredient(1, "clove", "garlic");
  ingredient(2, "tablespoon", "olive oil");
  ingredient(0.5, "teaspoon", "cumin");
};

hummus(1)
```
