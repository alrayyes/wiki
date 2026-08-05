---
publish: true
title: Rust Traits Syntax
created: 2020-09-17T16:32:03
modified: 2026-08-05T07:58:56.716Z
---

# Rust Traits Syntax

- [Definition](#definition)
- [Implementation](#implementation)
  - [Default Implementations](#default-implementations)
- [Traits as Parameters](#traits-as-parameters)
  - [Specifying Multiple Trait Bounds](#specifying-multiple-trait-bounds)
    - [Clearer Trait Bounds](#clearer-trait-bounds)
- [Return Types that Implement Traits](#return-types-that-implement-traits)

# Definition

```rust
#![allow(unused)]
fn main() {
    pub trait Summary {
        fn summarize(&self) -> String;
    }
}
```

# Implementation

```rust
#![allow(unused)]
fn main() {
    pub trait Summary {
        fn summarize(&self) -> String;
    }

    pub struct NewsArticle {
        pub headline: String,
        pub location: String,
        pub author: String,
        pub content: String,
    }

    impl Summary for NewsArticle {
        fn summarize(&self) -> String {
            format!("{}, by {} ({})", self.headline, self.author, self.location)
        }
    }

    pub struct Tweet {
        pub username: String,
        pub content: String,
        pub reply: bool,
        pub retweet: bool,
    }

    impl Summary for Tweet {
        fn summarize(&self) -> String {
            format!("{}: {}", self.username, self.content)
        }
    }
}
```

## Default Implementations

```rust
#![allow(unused)]
fn main() {
    pub trait Summary {
        fn summarize(&self) -> String {
            String::from("(Read more...)")
        }
    }

    pub struct NewsArticle {
        pub headline: String,
        pub location: String,
        pub author: String,
        pub content: String,
    }

    impl Summary for NewsArticle {}

    pub struct Tweet {
        pub username: String,
        pub content: String,
        pub reply: bool,
        pub retweet: bool,
    }

    impl Summary for Tweet {
        fn summarize(&self) -> String {
            format!("{}: {}", self.username, self.content)
        }
    }
}
```

# Traits as Parameters

```rust
pub trait Summary {
    fn summarize(&self) -> String;
}

pub struct NewsArticle {
    pub headline: String,
    pub location: String,
    pub author: String,
    pub content: String,
}

impl Summary for NewsArticle {
    fn summarize(&self) -> String {
        format!("{}, by {} ({})", self.headline, self.author, self.location)
    }
}

pub struct Tweet {
    pub username: String,
    pub content: String,
    pub reply: bool,
    pub retweet: bool,
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}

pub fn notify(item: &impl Summary) {
    println!("Breaking news! {}", item.summarize());
}
```

## Specifying Multiple Trait Bounds

```rust
pub fn notify(item: &(impl Summary + Display)) {
```

This also works on generic types:

```rust
pub fn notify<T: Summary + Display>(item: &T) {
```

### Clearer Trait Bounds

```rust
fn some_function<T: Display + Clone, U: Clone + Debug>(t: &T, u: &U) -> i32 {
```

is the same as

```rust
fn some_function<T, U>(t: &T, u: &U) -> i32
    where T: Display + Clone,
          U: Clone + Debug
{
```

# Return Types that Implement Traits

```rust
pub trait Summary {
    fn summarize(&self) -> String;
}

pub struct NewsArticle {
    pub headline: String,
    pub location: String,
    pub author: String,
    pub content: String,
}

impl Summary for NewsArticle {
    fn summarize(&self) -> String {
        format!("{}, by {} ({})", self.headline, self.author, self.location)
    }
}

pub struct Tweet {
    pub username: String,
    pub content: String,
    pub reply: bool,
    pub retweet: bool,
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}

fn returns_summarizable() -> impl Summary {
    Tweet {
        username: String::from("horse_ebooks"),
        content: String::from(
            "of course, as you probably already know, people",
        ),
        reply: false,
        retweet: false,
    }
}
```
