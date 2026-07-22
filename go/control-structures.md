# Go : Control Structures

## if

```go
if value, err := load(); err != nil {
    return err
} else {
    fmt.Println(value)
}
```

## for

```go
for index := 0; index < 10; index++ {
    fmt.Println(index)
}

for condition {
    // ...
}

for {
    break
}
```

## range

```go
for index, value := range values {
    fmt.Println(index, value)
}

for key, value := range configuration {
    fmt.Println(key, value)
}
```

## switch

```go
switch status {
case "ready":
    fmt.Println("Ready")
case "running", "waiting":
    fmt.Println("Active")
default:
    fmt.Println("Unknown")
}
```

## Control

```go
break
continue
fallthrough
```
