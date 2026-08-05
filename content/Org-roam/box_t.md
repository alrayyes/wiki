---
publish: true
title: Box<T>
created: 2020-09-29T13:56:09
modified: 2026-08-05T10:26:50.495Z
---

# Box<T>

- [Introduction](#introduction)
- [Reason to choose Box<T>](#reason-to-choose-boxt)
- [Usercases](#usercases)
  - [Type whose size can't be known at compile time](#type-whose-size-cant-be-known-at-compile-time)

# Introduction

Boxes allow you to store data on the heap rather than the stack. What remains on the stack is the pointer to the heap data.

Boxes don’t have performance overhead, other than storing their data on the heap instead of on the stack. But they don’t have many extra capabilities either. There are three typical user cases for Boxes:

- When you have a type whose size can’t be known at compile time and you want to use a value of that type in a context that requires an exact size
- When you have a large amount of data and you want to transfer ownership but ensure the data won’t be copied when you do so
- When you want to own a value and you care only that it’s a type that implements a particular trait rather than being of a specific type

```rust
fn main() {
    let b = Box::new(5);
    println!("b = {}", b);
}
```

# Reason to choose Box<T>

\~Box<T>~ allows immutable or mutable borrows checked at compile time; [Rc<T>](Rc<T>) allows only immutable borrows checked at compile time; [RefCell<T>](RefCell<T>) allows immutable or mutable borrows checked at runtime.

# Usercases

## Type whose size can't be known at compile time

When you have a type whose size can’t be known at compile time and you want to use a value of that type in a context that requires an exact size.

The following won't compile as the ~List~ type doesn't have a known size:

```rust
enum List {
    Cons(i32, List),
    Nil,
}

fn main() {}
```

This won't fly either:

```rust
enum List {
    Cons(i32, List),
    Nil,
}

use crate::List::{Cons, Nil};

fn main() {
    let list = Cons(1, Cons(2, Cons(3, Nil)));
}
```

With pointers all things are possible, huzzah:

```rust
enum List {
    Cons(i32, Box<List>),
    Nil,
}

use crate::List::{Cons, Nil};

fn main() {
    let _list = Cons(1, Box::new(Cons(2, Box::new(Cons(3, Box::new(Nil))))));
}
```
