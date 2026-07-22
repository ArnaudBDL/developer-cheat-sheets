# Go : Types

## Basic Types

```go
var enabled bool = true
var count int = 42
var unsigned uint = 42
var price float64 = 19.99
var character rune = 'G'
var octet byte = 0x47
var name string = "Go"
```

## Zero Values

```text
bool        false
numbers     0
string      ""
pointers    nil
slices      nil
maps        nil
channels    nil
interfaces  nil
```

## Conversions

```go
integer := int(price)
floating := float64(count)
text := string([]byte{'G', 'o'})
bytes := []byte(text)
runes := []rune(text)
```

## Custom Types and Aliases

```go
type UserID int64
type Identifier = string
```

## Pointers

```go
value := 42
pointer := &value
fmt.Println(*pointer)
*pointer = 100
```

## Type Switch

```go
switch value := input.(type) {
case string:
    fmt.Println("string", value)
case int:
    fmt.Println("int", value)
default:
    fmt.Printf("%T
", value)
}
```
