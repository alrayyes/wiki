---
publish: true
title: Golang Mutex
created: 2020-09-18T17:38:20
modified: 2026-08-05T10:26:50.510Z
---

# Golang Mutex

# Description

\[\[https://golang.org/pkg/sync/#Mutex]\[Mutex]] allows up to add locks to our data so it can be accessed safely in a concurrent manner. While locked other threads can't access the data. ~Mutexes~ should generally be used for \[\[https://github.com/golang/go/wiki/MutexOrChannel]\[managing state]].

# Syntax

```go
type Counter struct {
	mu    sync.Mutex
	value int
}

func (c *Counter) Inc() {
	c.mu.Lock()
	defer c.mu.Unlock()

	c.value++
}

func (c *Counter) Value() int {
	return c.value
}

func NewCounter() *Counter {
	return &Counter{}
}
```
