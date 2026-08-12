---
publish: true
title: Golang Mutex
created: 2020-09-18T17:38:20
modified: 2026-08-12T09:32:15.606Z
---

# Golang Mutex

## Description

[Mutex](https://golang.org/pkg/sync/#Mutex) allows up to add locks to our data so it can be accessed safely in a concurrent manner. While locked other threads can't access the data. ~Mutexes~ should generally be used for [managing state](https://github.com/golang/go/wiki/MutexOrChannel).

## Syntax

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
