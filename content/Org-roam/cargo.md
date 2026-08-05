---
publish: true
title: Cargo
created: 2020-09-18T18:07:50
modified: 2026-08-05T10:26:50.495Z
---

# Cargo

- [Description](#description)
- [Configuration](#configuration)
- [Commands](#commands)
  - [Create project](#create-project)
  - [Build & run project](#build--run-project)
    - [Backtrace](#backtrace)
  - [Publish to Crates.io](#publish-to-cratesio)
  - [Install package](#install-package)
  - [Linting & testing](#linting--testing)
    - [Check code](#check-code)
    - [Testing](#testing)
    - [Fix](#fix)
  - [Builds](#builds)
    - [Profiles](#profiles)
      - [dev](#dev)
      - [build](#build)
  - [Documentation](#documentation)
    - [Generation](#generation)
    - [Open in browser](#open-in-browser)

# Description

Cargo is Rust's build system and package manager.

# Configuration

- [Cargo.toml](Cargo.toml)

# Commands

## Create project

```shell
cargo new hello_cargo
```

## Build & run project

```shell
cargo run
```

### Backtrace

When you want to see an error backtrace set the ~RUST\_BACKTRACE~ environment variable:

```shell
RUST_BACKTRACE=1 cargo run
```

## Publish to Crates.io

```shell
cargo publish
```

## Install package

```shell
cargo install ripgrep
```

## Linting & testing

#### Check code

```shell
cargo check
```

#### Testing

```shell
cargo test
```

##### Backtrace

To backtrace set the ~RUST\_BACKTRACE~ environment variable:

```shell
RUST_BACKTRACE=1 cargo run
```

##### Threads

By default cargo runs test in parallel. For more control over this you can pass the number of threads you want to use. For example to only use 1 thread:

```shell
cargo test -- --test=threads=1
```

##### Show output for passing tests as well as failed tests

```shell
cargo test -- --show-output
```

##### Pass test name to cargo (this equals test function name)

```shell
cargo test one_hundred
```

##### Run ignored tests

```shell
cargo test -- --ignored
```

#### Fix

The rustfix tool is included with Rust installations and can automatically fix some compiler warnings.

```shell
cargo fix
```

## Builds

### Profiles

In Rust, release profiles are predefined and customizable profiles with different configurations that allow a programmer to have more control over various options for compiling code. Each profile is configured independently of the others.

Cargo has two main profiles: the ~dev~ profile Cargo uses when you run cargo build and the release profile Cargo uses when you run src\_shell{cargo build --release}. The ~dev~ profile is defined with good defaults for development, and the ~release~ profile has good defaults for release builds.

#### dev

```shell
cargo build
```

#### build

```shell
cargo build --release
```

## Documentation

See \[Rust Comments]\(Rust Comments) for documentation syntax.

### Generation

```shell
cargo doc
```

### Open in browser

```shell
cargo doc --open
```
