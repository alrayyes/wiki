---
publish: true
title: Golang tooling
created: 2020-08-26T19:15:08
---

# Golang tooling

## Documentation

Install godoc with src\_shell{go get golang.org/x/tools/cmd/godoc}

Documentation can be generated with

```shell
godoc --http :8000
```

## Linters

- [errcheck](https://github.com/kisielk/errcheck)

## Testing

### Code coverage

```shell
go test -cover
```

### Race conditions

```shell
go test -race
```

### Vetting

Vet examines Go source code and reports suspicious constructs, such as Printf calls whose arguments do not align with the format string. Vet uses heuristics that do not guarantee all reports are genuine problems, but it can find errors not caught by the compilers.

```shell
go vet
```
