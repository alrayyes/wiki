---
publish: true
title: Golang Embedding
created: 2020-09-28T19:32:45
modified: 2026-08-05T10:26:50.499Z
---

# Golang Embedding

- [Description](#description)
- [Interfaces](#interfaces)
- [Structs](#structs)

# Description

\[\[https://golang.org/doc/effective\_go.html#embedding]\[Embedding]] is Gos answer to subclasses. There's one caveat:

\#+BEGIN\_QUOTE
There's an important way in which embedding differs from subclassing. When we embed a type, the methods of that type become methods of the outer type, but when they are invoked the receiver of the method is the inner type, not the outer one.
\#+END\_QUOTE

# Interfaces

```go
type Reader interface {
    Read(p []byte) (n int, err error)
}

type Writer interface {
    Write(p []byte) (n int, err error)
}

type ReadWriter interface {
    Reader
    Writer
}
```

\~ReadWriter~ "extends" ~Reader~ & ~Writer~ in the example above.

# Structs

```go
type ReadWriter struct {
    ,*Reader  // *bufio.Reader
    ,*Writer  // *bufio.Writer
}

func (rw *ReadWriter) Read(p []byte) (n int, err error) {
    return rw.reader.Read(p)
}
```
