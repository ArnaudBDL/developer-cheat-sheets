# Go : Concurrency

## Goroutines

```go
go process(item)
```

## Channels

```go
results := make(chan int)

go func() {
    results <- calculate()
}()

result := <-results
```

## Buffered Channel

```go
jobs := make(chan Job, 10)
jobs <- job
close(jobs)
```

## select

```go
select {
case result := <-results:
    return result, nil
case <-ctx.Done():
    return 0, ctx.Err()
case <-time.After(5 * time.Second):
    return 0, errors.New("timeout")
}
```

## WaitGroup

```go
var group sync.WaitGroup

for _, item := range items {
    group.Add(1)
    go func(item Item) {
        defer group.Done()
        process(item)
    }(item)
}

group.Wait()
```

## Mutex

```go
var mutex sync.Mutex

mutex.Lock()
count++
mutex.Unlock()
```

## Race Detection

```bash
go test -race ./...
go run -race .
go build -race ./...
```
