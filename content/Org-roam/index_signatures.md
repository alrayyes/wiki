---
publish: true
title: TypeScript Index Signatures
created: 2020-10-08T09:22:25
modified: 2026-08-05T07:58:56.686Z
---

# TypeScript Index Signatures

- [Introduction](#introduction)
- [Syntax](#syntax)
  - [Declaring an index signature](#declaring-an-index-signature)
  - [Interfaces](#interfaces)
  - [String literals](#string-literals)
  - [Generics](#generics)

# Introduction

An \[JavaScript Objects]\(JavaScript Objects) in [JavaScript](JavaScript) can be accessed with a string to hold a reference to any other JavaScript object.

```typescript
let foo: any = {};
foo['Hello'] = 'World';
console.log(foo['Hello']); // World
```

```typescript
class Foo {
  constructor(public message: string){};
  log(){
    console.log(this.message)
  }
}

let foo: any = {};
foo['Hello'] = new Foo('World');
foo['Hello'].log(); // World
```

```typescript
let obj = {
  toString(){
    console.log('toString called')
    return 'Hello'
  }
}

let foo: any = {};
foo[obj] = 'World'; // toString called
console.log(foo[obj]); // toString called, World
console.log(foo['Hello']); // World
```

# Syntax

## Declaring an index signature

```typescript
let foo:{ [index:string] : {message: string} } = {};

/**
 * Must store stuff that conforms to the structure
 */
/** Ok */
foo['a'] = { message: 'some message' };
/** Error: must contain a `message` of type string. You have a typo in `message` */
foo['a'] = { messages: 'some message' };

/**
 * Stuff that is read is also type checked
 */
/** Ok */
foo['a'].message;
/** Error: messages does not exist. You have a typo in `message` */
foo['a'].messages;
```

## Interfaces

As soon as you have a string index signature, all explicit members must also conform to that index signature. A few \[TypeScript Interfaces]\(TypeScript Interfaces) examples:

```typescript
interface Foo {
  x: number;
}
let foo: Foo = {x:1,y:2};
​
// Directly
foo['x']; // number
​
// Indirectly
let x = 'x'
foo[x]; // number
```

## String literals

\[TypeScript Literal Types]\(TypeScript Literal Types) can also be used in the declaration:

```typescript
type Index = 'a' | 'b' | 'c'
type FromIndex = { [k in Index]?: number }

const good: FromIndex = {b:1, c:2}

// Error:
// Type '{ b: number; c: number; d: number; }' is not assignable to type 'FromIndex'.
// Object literal may only specify known properties, and 'd' does not exist in type 'FromIndex'.
const bad: FromIndex = {b:1, c:2, d:3};
```

## Generics

\[TypeScript Generics]\(TypeScript Generics) can also be used:

```typescript
type FromSomeIndex<K extends string> = { [key in K]: number }
```
