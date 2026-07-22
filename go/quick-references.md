# Go : Quick References

## Project

```bash
go version
go mod init example.com/project
go mod tidy
go run .
go build ./...
go test ./...
go fmt ./...
```

## Language

```go
value, err := operation()
if err != nil {
    return fmt.Errorf("operation failed: %w", err)
}

for index, item := range items {
    fmt.Println(index, item)
}
```

## Concurrency

```go
go worker(ctx, jobs)

select {
case result := <-results:
    fmt.Println(result)
case <-ctx.Done():
    return ctx.Err()
}
```
