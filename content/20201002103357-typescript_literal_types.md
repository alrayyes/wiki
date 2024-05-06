---
id: d6b6005e-bd66-4524-b1f4-d3b27c8d9c46
title: TypeScript Literal Types
---

# Introduction

Literals are *exact* values that are JavaScript primitives.

# Types

-   [String](20201123100551-typescript_string_literal_type)
-   [Boolean](20201123100939-typescript_boolean_literal_type)
-   [Number](20201123101123-typescript_number_literal_type)
-   [Template Literal
    String](20201123101810-typescript_template_literal_string_type)

# Type Guards

-   [TypeScript Literal Type
    Guard](20201124091025-typescript_literal_type_guard)

# Inference

TypeScript is not all knowing. The following won't fly:

``` typescript
function iTakeFoo(foo: 'foo') { }
const test = {
  someProp: 'foo'
};
iTakeFoo(test.someProp); // Error: Argument of type string is not assignable to parameter of type 'foo'
```

TypeScript infers `test` to be of type `{someProp: string`}. There are a
couple of ways to fix this:

``` typescript
function iTakeFoo(foo: 'foo') { }
const test = {
  someProp: 'foo' as 'foo'
};
iTakeFoo(test.someProp); // Okay!
```

``` typescript
function iTakeFoo(foo: 'foo') { }
type Test = {
  someProp: 'foo',
}
const test: Test = { // Annotate - inferred someProp is always === 'foo'
  someProp: 'foo'
};
iTakeFoo(test.someProp); // Okay!
```
