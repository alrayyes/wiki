---
publish: true
title: TypeScript Literal Type Guard
created: 2020-11-24T09:10:25
modified: 2026-08-12T09:32:15.642Z
---

# TypeScript Literal Type Guard

## Description

Use [[TypeScript Literal Types]] to narrow down the object type in a conditional block

## Syntax

```typescript
type TriState = 'yes' | 'no' | 'unknown';
​
function logOutState(state:TriState) {
  if (state == 'yes') {
    console.log('User selected yes');
  } else if (state == 'no') {
    console.log('User selected no');
  } else {
    console.log('User has not made a selection yet');
  }
}
```

```typescript
type Foo = {
  kind: 'foo', // Literal type
  foo: number
}
type Bar = {
  kind: 'bar', // Literal type
  bar: number
}
​
function doStuff(arg: Foo | Bar) {
    if (arg.kind === 'foo') {
        console.log(arg.foo); // OK
        console.log(arg.bar); // Error!
    }
    else {  // MUST BE Bar!
        console.log(arg.foo); // Error!
        console.log(arg.bar); // OK
    }
}
```
