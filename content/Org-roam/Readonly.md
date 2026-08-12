---
publish: true
title: Readonly
created: 2020-10-05T17:12:53
modified: 2026-08-12T09:32:15.628Z
---

# Readonly

## Introduction

[[TypeScript]] type system allows you to mark individual properties on [[TypeScript Interfaces]], [[TypeScript Type Alias]] and [[TypeScript Classes]] properties as ~readonly~.

## Examples

### interface

\#+BEGIN\_SRC typescript
function foo(config: {
readonly bar: number,
readonly bas: number}) {// ..
}

let config = { bar: 123, bas: 123 };
foo(config);
// You can be sure that `config` isn't changed 🌹
\#+END\_SRC

### type

```typescript
type Foo = {
    readonly bar: number;
    readonly bas: number;
}
​
// Initialization is okay
let foo: Foo = { bar: 123, bas: 456 };
​
// Mutation is not
foo.bar = 456; // Error: Left-hand side of assignment expression cannot be a constant or a read-only property
```

### class property

```typescript
class Foo {
    readonly bar = 1; // OK
    readonly baz: string;
    constructor() {
        this.baz = "hello"; // OK
    }
}
```

```typescript
type Foo = {
  bar: number;
  bas: number;
}

type FooReadonly = Readonly<Foo>;

let foo: Foo = {bar: 123, bas: 456};
let fooReadonly: FooReadonly = {bar: 123, bas: 456};

foo.bar = 456; // Okay
fooReadonly.bar = 456; // ERROR: bar is readonly
```
