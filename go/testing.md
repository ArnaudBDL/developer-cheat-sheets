# Go : Testing

## Basic Test

```go
package calculator

import "testing"

func TestAdd(t *testing.T) {
    actual := Add(2, 3)
    expected := 5

    if actual != expected {
        t.Fatalf("Add(2, 3) = %d; want %d", actual, expected)
    }
}
```

## Table-Driven Test

```go
func TestAdd(t *testing.T) {
    tests := []struct {
        name     string
        left     int
        right    int
        expected int
    }{
        {name: "positive", left: 2, right: 3, expected: 5},
        {name: "negative", left: -2, right: 1, expected: -1},
    }

    for _, test := range tests {
        t.Run(test.name, func(t *testing.T) {
            if actual := Add(test.left, test.right); actual != test.expected {
                t.Fatalf("got %d; want %d", actual, test.expected)
            }
        })
    }
}
```

## Run Tests

```bash
go test ./...
go test -v ./...
go test -run TestAdd ./...
go test -race ./...
go test -cover ./...
go test -coverprofile=coverage.out ./...
go tool cover -html=coverage.out
```

## Benchmark

```go
func BenchmarkAdd(b *testing.B) {
    for b.Loop() {
        Add(2, 3)
    }
}
```

```bash
go test -bench=. -benchmem ./...
```

## Fuzz Test

```go
func FuzzAdd(f *testing.F) {
    f.Add(2, 3)
    f.Fuzz(func(t *testing.T, left, right int) {
        _ = Add(left, right)
    })
}
```

```bash
go test -fuzz=FuzzAdd
```
