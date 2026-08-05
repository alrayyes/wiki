---
publish: true
title: Rust Iterators
created: 2020-09-23T15:00:06
modified: 2026-08-05T07:58:56.687Z
---

# Rust Iterators

- [Syntax](#syntax)
- [Iterator Trait](#iterator-trait)
- [Iterator methods](#iterator-methods)
  - [next](#next)
  - [sum](#sum)
- [Methods that produce other Iterators](#methods-that-produce-other-iterators)
- [Creating your own Iterators](#creating-your-own-iterators)

# Syntax

```rust
fn main() {
    let v1 = vec![1, 2, 3];

    let v1_iter = v1.iter();

    for val in v1_iter {
        println!("Got: {}", val);
    }
}
```

# Iterator Trait

All iterators implement a \[Rust Traits Syntax]\(Rust Traits Syntax) named \[\[https://doc.rust-lang.org/std/iter/trait.Iterator.html]\[Iterator]]

```rust
#![allow(unused)]
fn main() {
    pub trait Iterator {
        type Item;

        fn next(&mut self) -> Option<Self::Item>;

        // methods with default implementations elided
    }
}
```

# Iterator methods

## next

```rust
#[cfg(test)]
mod tests {
    #[test]
    fn iterator_demonstration() {
        let v1 = vec![1, 2, 3];

        let mut v1_iter = v1.iter();

        assert_eq!(v1_iter.next(), Some(&1));
        assert_eq!(v1_iter.next(), Some(&2));
        assert_eq!(v1_iter.next(), Some(&3));
        assert_eq!(v1_iter.next(), None);
    }
}

fn main() {}
```

## sum

```rust
#[cfg(test)]
mod tests {
    #[test]
    fn iterator_sum() {
        let v1 = vec![1, 2, 3];

        let v1_iter = v1.iter();

        let total: i32 = v1_iter.sum();

        assert_eq!(total, 6);
    }
}

fn main() {}
```

# Methods that produce other Iterators

By their nature iterators are lazy so the following won't work:

```rust
fn main() {
    let v1: Vec<i32> = vec![1, 2, 3];

    v1.iter().map(|x| x + 1);
}
```

The Iterator must be consumed, using the \[\[https://doc.rust-lang.org/std/iter/trait.Iterator.html#method.collect]\[collect]] method:

```rust
fn main() {
    let v1: Vec<i32> = vec![1, 2, 3];

    let v2: Vec<_> = v1.iter().map(|x| x + 1).collect();

    assert_eq!(v2, vec![2, 3, 4]);
}
```

# Creating your own Iterators

```rust
struct Counter {
    count: u32,
}

impl Counter {
    fn new() -> Counter {
        Counter { count: 0 }
    }
}

impl Iterator for Counter {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        if self.count < 5 {
            self.count += 1;
            Some(self.count)
        } else {
            None
        }
    }
}

fn main() {
    let counter = Counter::new();

    for val in counter {
        println!("Got: {}", val);
    }
}
```
