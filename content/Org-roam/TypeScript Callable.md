---
publish: true
title: TypeScript Callable
created: 2020-10-01T11:21:26
modified: 2026-08-12T09:44:58.361Z
---

# TypeScript Callable

## Examples

### Basic

```typescript
interface ReturnString {
  (): string
}

declare const foo: ReturnString;
const bar = foo(); // bar is inferred as a string
```

```typescript
interface Complex {
  (foo: string, bar?: number, ...others: boolean[]): number;
}
```

### Overloading

```typescript
interface Overloaded {
    (foo: string): string
    (foo: number): number
}

// example implementation
function stringOrNumber(foo: number): number;
function stringOrNumber(foo: string): string;
function stringOrNumber(foo: any): any {
    if (typeof foo === 'number') {
        return foo * foo;
    } else if (typeof foo === 'string') {
        return `hello ${foo}`;
    }
}

const overloaded: Overloaded = stringOrNumber;

// example usage
const str = overloaded(''); // type of `str` is inferred as `string`
const num = overloaded(123); // type of `num` is inferred as `number`
```

```typescript
const overloaded: {
  (foo: string): string
  (foo: number): number
} = (foo: any) => foo;
```

### Arrow Syntax

```typescript
const simple: (foo: number) => string
    = (foo) => foo.toString();
```

### Newable

Newable is just a special type of callable type annotation with the prefix new. It simply means that you need to invoke with new:

```typescript
interface CallMeWithNewToGetString {
  new(): string
}
// Usage
declare const Foo: CallMeWithNewToGetString;
const bar = new Foo(); // bar is inferred to be of type string
```
