# Go : Installation

## Verify Installation

```bash
go version
go env
```

## macOS

```bash
brew install go
brew upgrade go
go version
```

## Linux Archive

```bash
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf goVERSION.linux-amd64.tar.gz
export PATH="$PATH:/usr/local/go/bin"
go version
```

## Create a Project

```bash
mkdir application
cd application
go mod init example.com/application
```

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Go")
}
```

```bash
go run .
go build ./...
go install ./...
```

## Go Tools

```bash
go help
go env GOPATH GOROOT GOVERSION
go fmt ./...
go vet ./...
go test ./...
```
