# Go : Arrays and Slices

## Arrays

```go
var values [3]int
numbers := [3]int{10, 20, 30}
inferred := [...]string{"one", "two", "three"}
```

## Slices

```go
values := []int{10, 20, 30}
values = append(values, 40)
subset := values[1:3]
```

## Make, Length and Capacity

```go
values := make([]int, 0, 10)
fmt.Println(len(values))
fmt.Println(cap(values))
```

## Copy

```go
source := []int{1, 2, 3}
destination := make([]int, len(source))
copy(destination, source)
```

## Delete an Element

```go
index := 1
values = append(values[:index], values[index+1:]...)
```

## Iterate

```go
for index, value := range values {
    fmt.Println(index, value)
}
```
