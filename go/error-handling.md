# Go : Error Handling

## Return Errors

```go
func load(path string) ([]byte, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        return nil, err
    }

    return data, nil
}
```

## Wrap Errors

```go
if err != nil {
    return fmt.Errorf("read configuration %q: %w", path, err)
}
```

## Inspect Errors

```go
if errors.Is(err, os.ErrNotExist) {
    // Handle missing file.
}

var pathError *os.PathError
if errors.As(err, &pathError) {
    fmt.Println(pathError.Path)
}
```

## Sentinel and Custom Errors

```go
var ErrNotFound = errors.New("not found")

type ValidationError struct {
    Field string
}

func (err ValidationError) Error() string {
    return "invalid field: " + err.Field
}
```

## panic and recover

Use ordinary error values for expected failures. Reserve `panic` for unrecoverable programmer or initialization failures, and use `recover` only at carefully chosen boundaries.
