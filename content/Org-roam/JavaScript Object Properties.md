---
publish: true
title: JavaScript Object Properties
created: 2020-11-13T09:11:10
modified: 2026-08-12T10:26:13.180Z
---

# JavaScript Object Properties

## Description

Values of the type [[JavaScript Objects]] are arbitrary collections of properties

## Syntax

```js
let tralala = {
  distro: "Arch",
  useWindows: false,
  aListOfRandomThings: ["spoon", "fork", "modem", "keychain"],
};

console.log(tralala.distro);
console.log(tralala.useWindows);
console.log(tralala.aListOfRandomThings);
```

## Invalid binding names

Properties with invalid binding names or numbers must be quoted:

```js
let weirdObject = {
    tralala: "Chipmunk",
    "this is a long binding name with spaces": "Fill in some nonsensse here"
}

console.log(weirdObject)
```

## Non existant property

Reading a non existant property returns ~undefined~

```js
let Object = {
  thisExists: true,
};

console.log(Object.undefinedProperty); // undefined
```
