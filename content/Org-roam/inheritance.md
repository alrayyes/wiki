---
publish: true
title: JavaScript Class Inheritance
created: 2020-10-08T09:06:13
modified: 2026-08-05T10:26:50.503Z
---

# JavaScript Class Inheritance

# Example

Classes in JavaScript can inherit from each other

```js
class Parent {
    constructor(name, parentChild = "Parent") {
        this.parentChild = parentChild
        this.name = name
    }

    speak(line) {
        console.log(`${this.parentChild} ${this.name} says '${line}'`)
    }
}

class Child extends Parent {
    constructor(name){
        super(name, "Child")
    }
}

let parent = new Parent("Father");
let child = new Child("Gregory");
parent.speak("Get off my lawn!");
child.speak("Make me old man!");
```

The use of the word ~extends~ indicates that this class shouldn’t be directly based on the default \[JavaScript Objects]\(JavaScript Objects) prototype but on some other class. This is called the superclass. The derived class is the subclass. The superclass's constructor and methods can be called by appending ~super~ in front.
