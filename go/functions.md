# Go : Functions

## Basic Function

```go
func add(left int, right int) int {
    return left + right
}
```

## Grouped Parameters

```go
func multiply(left, right int) int {
    return left * right
}
```

## Multiple Return Values

```go
func divide(left, right float64) (float64, error) {
    if right == 0 {
        return 0, errors.New("division by zero")
    }

    return left / right, nil
}
```

## Variadic Function

```go
func total(values ...int) int {
    sum := 0
    for _, value := range values {
        sum += value
    }
    return sum
}

result := total(1, 2, 3)
```

## Function Values and Closures

```go
operation := func(left, right int) int {
    return left + right
}

func counter() func() int {
    count := 0
    return func() int {
        count++
        return count
    }
}
```

## defer

```go
file, err := os.Open("data.txt")
if err != nil {
    return err
}
defer file.Close()
```
