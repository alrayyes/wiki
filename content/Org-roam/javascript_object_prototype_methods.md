---
publish: true
title: JavaScript Object Prototype Methods
created: 2020-11-13T09:32:04
modified: 2026-08-05T10:26:50.505Z
---

# JavaScript Object Prototype Methods

# Description

JavaScript \[JavaScript Objects]\(JavaScript Objects) have methods.

# Syntax

## Basic syntax

Objects can also have methods

```js
let robot = {};
robot.speak = function(name) {
    console.log(`${name} is alive!`)
}

robot.speak("Johnny 5")
```

## Properties

Of course methods can use object properties and functions can be passed as properties

```js
let robot = {name: "Johnny 5", speak};
function speak(state) {
    console.log(`${this.name} is ${state}!`)
}

robot.speak("alive")
```

## This

\~this~ parameter can also be passed explicitly using a functions ~call~ method, if that's socially acceptable in your culture:

```js
let robot = {name: "Johnny 5"};

function speak(state) {
    console.log(`${this.name} is ${state}!`)
}

speak.call(robot, "alive")

```
