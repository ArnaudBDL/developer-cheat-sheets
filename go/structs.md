# Go : Structs

## Declare and Initialize

```go
type User struct {
    ID     int64
    Name   string
    Active bool
}

user := User{
    ID:     42,
    Name:   "Arnaud",
    Active: true,
}
```

## Methods

```go
func (user User) DisplayName() string {
    return user.Name
}

func (user *User) Rename(name string) {
    user.Name = name
}
```

## Embedding

```go
type Timestamp struct {
    CreatedAt time.Time
}

type Article struct {
    Timestamp
    ID    int64
    Title string
}
```

## Tags

```go
type Payload struct {
    Name  string `json:"name" validate:"required"`
    Email string `json:"email" validate:"required,email"`
}
```

## Anonymous Struct

```go
response := struct {
    Status string `json:"status"`
}{Status: "ok"}
```
