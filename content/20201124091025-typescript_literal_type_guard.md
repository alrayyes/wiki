---
id: 9c3b63f1-db7d-4d11-9755-2ff0dcfeddf4
title: TypeScript Literal Type Guard
---

# Description

Use [literal types](20201002103357-typescript_literal_types) to narrow
down the object type in a conditional block

# Syntax

``` typescript
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

``` typescript
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
