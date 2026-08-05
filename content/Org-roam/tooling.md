---
publish: true
title: Rust tooling
created: 2020-08-27T17:10:36
modified: 2026-08-05T10:26:50.519Z
---

# Rust tooling

- [Rustc](#rustc)
- [Cargo](#cargo)
  - [Cargo commands](#cargo-commands)
    - [Create project](#create-project)
    - [Build project](#build-project)
    - [Build & run project](#build--run-project)
    - [Check code](#check-code)
    - [Build for release](#build-for-release)
  - [Cargo.toml](#cargotoml)

# Rustc

Rustc handles Rust compilation src\_shell{rustc main.rs}

# Cargo

Cargo is Rust's build system and package manager

## Cargo commands

### Create project

```shell
cargo new hello_cargo
```

### Build project

```shell
cargo build
```

### Build & run project

```shell
cargo run
```

#### Backtrace

When you want to see an error backtrace set the ~RUST\_BACKTRACE~ environment variable:

```shell
RUST_BACKTRACE=1 cargo run
```

### Check code

```shell
cargo check
```

### Build for release

```shell
cargo build --release
```

## Cargo.toml

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"

[dependencies]
```
