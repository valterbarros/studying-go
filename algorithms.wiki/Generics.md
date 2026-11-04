### Generic types

The old way to run generics is using interface and duplicating code   
But now go has Generics as default a example of generics

```go
type code[T any] struct {
	code T
}
```

### The `comparable` constraint   
This constraint make sure that only comparable type can be accepted   
Comparable types is one that can use `==` and `!=`, int, string, etc
```go
func isEqual[T comparable](s T, x T) bool {
	return s == x
}
```

### Generics on struct methods
```go
type List[T any] struct {
	next *List[T]
	val  T
}
```

struct method type:
```go
func (l *List[T]) getNext() *List[T] {
	return l.next
}
```

See no need to type the `T` because it is got from List struct type   
```go func (l *List[T]) getNext() *List[T] {```

### Code struct can receive `any` type

It is possible to have string type
```go
code1 := code[string]{"123f1"}
fmt.Println("code is: ", code1.code)
// It is possible to have int type
code2 := code[int]{123}
fmt.Println("code2 is: ", code2.code)
```

Using generic function
```go
fmt.Println("isEqual: ", isEqual("a", "b"))
```

### Using the generic method

note the [int] it is obrigatory
```go
node2 := List[int]{next: nil, val: 2}
node1 := List[int]{next: &node2, val: 1}
// should return node2 value(2)
fmt.Println(node1, node1.getNext().val)
```
