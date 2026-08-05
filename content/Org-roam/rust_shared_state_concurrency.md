---
publish: true
title: Rust Shared-State Concurrency
created: 2020-09-30T12:37:49
modified: 2026-08-05T10:26:50.514Z
---

# Rust Shared-State Concurrency

- [Mutex<T>](#mutext)
  - [Single thread example](#single-thread-example)
  - [Multiple thread example](#multiple-thread-example)

# Mutex<T>

## Single thread example

```rust
use std::sync::Mutex;

fn main() {
    let m = Mutex::new(5);

    {
        let mut num = m.lock().unwrap();
        *num = 6;
    }

    println!("m = {:?}", m);
}
```

## Multiple thread example

```rust
use std::sync::{Arc, Mutex};
use std::thread;

fn main() {
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];

    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            let mut num = counter.lock().unwrap();

            *num += 1;
        });
        handles.push(handle);
    }

    for handle in handles {
        handle.join().unwrap();
    }

    println!("Result: {}", *counter.lock().unwrap());
}
```
