# Go : Interfaces

## Declare an Interface

```go
type Writer interface {
    Write(data []byte) (int, error)
}
```

Types satisfy interfaces implicitly by implementing the required methods.

## Use an Interface

```go
func writeMessage(writer io.Writer, message string) error {
    _, err := io.WriteString(writer, message)
    return err
}
```

## Interface Composition

```go
type ReadWriter interface {
    io.Reader
    io.Writer
}
```

## Type Assertion

```go
value, ok := input.(string)
if !ok {
    return errors.New("expected string")
}
```

## Type Switch

```go
switch value := input.(type) {
case string:
    fmt.Println(value)
case fmt.Stringer:
    fmt.Println(value.String())
default:
    fmt.Printf("unsupported %T
", value)
}
```

## Compile-Time Check

```go
var _ io.Writer = (*bytes.Buffer)(nil)
```
