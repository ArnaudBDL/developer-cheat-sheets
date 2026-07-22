# Go : Packages

## Package Layout

```text
application/
├── cmd/application/main.go
├── internal/service/service.go
├── internal/store/store.go
├── go.mod
└── go.sum
```

## Declare a Package

```go
package service

func Execute() error {
    return nil
}
```

## Import Packages

```go
import (
    "fmt"

    "example.com/application/internal/service"
)
```

## Import Aliases

```go
import storage "example.com/application/internal/store"
```

## Package Documentation

```go
// Package service contains application business services.
package service
```

## Inspect Packages

```bash
go list ./...
go list -deps ./...
go doc PACKAGE
go doc PACKAGE.Symbol
go vet ./...
```
