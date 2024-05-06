---
id: 3d5c7ec9-30af-4931-b6ab-2caa687f5951
title: JavaScript Object Properties
---

# Description

Values of the type [object](20200826201605-objects) are arbitrary
collections of properties

# Syntax

``` javascript
let tralala = {
  distro: "Arch",
  useWindows: false,
  aListOfRandomThings: ["spoon", "fork", "modem", "keychain"],
};

console.log(tralala.distro);
console.log(tralala.useWindows);
console.log(tralala.aListOfRandomThings);
```

# Invalid binding names

Properties with invalid binding names or numbers must be quoted:

``` javascript
let weirdObject = {
    tralala: "Chipmunk",
    "this is a long binding name with spaces": "Fill in some nonsensse here"
}

console.log(weirdObject)
```

# Non existant property

Reading a non existant property returns `undefined`

``` javascript
let Object = {
  thisExists: true,
};

console.log(Object.undefinedProperty); // undefined
```
