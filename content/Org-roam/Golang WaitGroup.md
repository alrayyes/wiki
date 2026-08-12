---
publish: true
title: Golang WaitGroup
created: 2020-09-18T17:45:48
---

# Golang WaitGroup

## Description

A [WaitGroup](https://golang.org/pkg/sync/#WaitGroup) waits for a collection of goroutines to finish. The main goroutine calls Add to set the number of goroutines to wait for. Then each of the goroutines runs and calls Done when finished. At the same time, Wait can be used to block until all goroutines have finished.

A WaitGroup must not be copied after first use.

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

wantedCount := 1000
counter := NewCounter()

var wg sync.WaitGroup
wg.Add(wantedCount)

for i := 0; i < wantedCount; i++ {
	go func(w *sync.WaitGroup) {
		counter.Inc()
		w.Done()
	}(&wg)
}

wg.Wait()
```
