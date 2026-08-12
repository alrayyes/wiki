---
publish: true
title: TypeScript Literal Types
created: 2020-10-02T10:33:57
---

# TypeScript Literal Types

## Introduction

Literals are /exact/ values that are JavaScript primitives.

## Types

- [[TypeScript String Literal Type]]
- [[TypeScript Boolean Literal Type]]
- [[TypeScript Number Literal Type]]
- [[TypeScript Template Literal String Type]]

## Type Guards

- [[TypeScript Literal Type Guard]]

## Inference

TypeScript is not all knowing. The following won't fly:

```typescript
function iTakeFoo(foo: 'foo') { }
const test = {
  someProp: 'foo'
};
iTakeFoo(test.someProp); // Error: Argument of type string is not assignable to parameter of type 'foo'
```

TypeScript infers ~test~ to be of type src\_typescript{{someProp: string}}. There are a couple of ways to fix this:

```typescript
function iTakeFoo(foo: 'foo') { }
const test = {
  someProp: 'foo' as 'foo'
};
iTakeFoo(test.someProp); // Okay!
```

```typescript
function iTakeFoo(foo: 'foo') { }
type Test = {
  someProp: 'foo',
}
const test: Test = { // Annotate - inferred someProp is always === 'foo'
  someProp: 'foo'
};
iTakeFoo(test.someProp); // Okay!
```
