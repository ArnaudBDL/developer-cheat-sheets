# Go : Syntax

## Program Structure

```go
package main

import (
    "fmt"
    "time"
)

const applicationName = "Application"

func main() {
    fmt.Println(applicationName, time.Now())
}
```

## Variables and Constants

```go
var name string = "Go"
var count int
active := true
const timeout = 30
```

## Comments

```go
// Single-line comment

/*
Multi-line comment
*/
```

## Formatting

```bash
gofmt -w .
go fmt ./...
```

## Exported Identifiers

```go
func PublicFunction() {}
func privateFunction() {}
```

Identifiers beginning with an uppercase letter are exported from their package.
