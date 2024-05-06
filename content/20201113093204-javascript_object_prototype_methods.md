---
id: 2c9b94b2-a652-42d7-97ee-731686d29e58
title: JavaScript Object Prototype Methods
---

# Description

JavaScript [objects](20200826201605-objects) have methods.

# Syntax

## Basic syntax

Objects can also have methods

``` javascript
let robot = {};
robot.speak = function(name) {
    console.log(`${name} is alive!`)
}

robot.speak("Johnny 5")
```

## Properties

Of course methods can use object properties and functions can be passed
as properties

``` javascript
let robot = {name: "Johnny 5", speak};
function speak(state) {
    console.log(`${this.name} is ${state}!`)
}

robot.speak("alive")
```

## This

`this` parameter can also be passed explicitly using a functions `call`
method, if that's socially acceptable in your culture:

``` javascript
let robot = {name: "Johnny 5"};

function speak(state) {
    console.log(`${this.name} is ${state}!`)
}

speak.call(robot, "alive")

```
