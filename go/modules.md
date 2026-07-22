# Go : Modules

## Initialize a Module

```bash
go mod init example.com/application
```

## Dependencies

```bash
go get example.com/module@latest
go get example.com/module@v1.2.3
go get example.com/module@none
go mod tidy
go mod download
```

## Inspect

```bash
go list -m all
go list -m -versions example.com/module
go mod graph
go mod why example.com/module
go mod verify
```

## Replace for Local Development

```go
module example.com/application

go 1.26

replace example.com/library => ../library
```

## Workspace

```bash
go work init ./application ./library
go work use ./another-module
go work sync
```

Commit `go.mod` and `go.sum`. Avoid committing a local-only `replace` directive intended solely for an individual workstation.
