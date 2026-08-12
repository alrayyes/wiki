---
publish: true
title: Golang Errors
created: 2020-09-09T20:24:54
modified: 2026-08-12T10:26:13.170Z
---

# Golang Errors

## Basics

Go supports Errors

```go

import (
	"errors"
	"fmt"
)

func ThrowError(throwError bool) error {
	if throwError {
		return errors.New("This is an error")
	}

	fmt.Println("No error was thrown!")
	return nil
}

func main() {
	ThrowError(true)
	ThrowError(false)
}
```

## Wrappers

It appears to be good practice to make errors a ~const~. This example uses the Error [[Golang interfaces]]:

```go
const (
    ErrNotFound   = DictionaryErr("could not find the word you were looking for")
    ErrWordExists = DictionaryErr("cannot add word because it already exists")
)

type DictionaryErr string

func (e DictionaryErr) Error() string {
    return string(e)
}
```

## Handy Links

- Constant errors[^constanterrors]

## Footnotes

[^constanterrors]: https://dave.cheney.net/2016/04/07/constant-errors
