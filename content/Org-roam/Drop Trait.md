---
publish: true
title: Drop Trait
created: 2020-09-29T14:29:32
modified: 2026-08-12T09:44:58.320Z
---

# Drop Trait

## Introduction

\~Drop~ lets you customize what happens when a value is about to go out of scope, ie: to release resources like files or network connections.

## Example

```rust
struct CustomSmartPointer {
    data: String,
}

impl Drop for CustomSmartPointer {
    fn drop(&mut self) {
        println!("Dropping CustomSmartPointer with data `{}`!", self.data);
    }
}

fn main() {
    let _c = CustomSmartPointer {
        data: String::from("my stuff"),
    };
    let _d = CustomSmartPointer {
        data: String::from("other stuff"),
    };
    println!("CustomSmartPointers created.");
}
```
