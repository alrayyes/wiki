---
publish: true
title: predicate
created: 2020-11-26T10:13:27
modified: 2026-08-05T10:26:50.513Z
---

# predicate

# Origin

Latin praedicatus "something declared"

# Definition

A function that returns a single boolean value

# Examples

type Predicate = () => boolean

function isTurkey(x: string) {
return x === 'turkey'
}

interface Dog {
bark: 'dog'
}

interface Cat {
meow: 'cat'
}

function isCat(animal): animal is Cat {
return (animal as Cat).meow !== undefined
}

function makeSound(animal: Cat | Dog) {
if (isCat(animal)) {
animal.meow
} else {
animal.bark
}
}
