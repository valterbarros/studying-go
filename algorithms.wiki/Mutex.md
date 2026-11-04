```go
type SafeCounter struct {
	mu     sync.Mutex
	mapper map[string]int
}
```

```go
func (s *SafeCounter) increment(key string) {
	// This function is locked after next instruction
	// if another call to incremented is made it don't continue
	// The door is closed
	s.mu.Lock()
	// The lock is not related with mapper
	s.mapper[key]++
	// Unlock function here
	// The door has opened
	s.mu.Unlock()
}
```

```go
sf := SafeCounter{mapper: map[string]int{}}
for range 1000 {
	go sf.increment("key")
}
fmt.Println("key incremented: ", sf.mapper["key"])
```
