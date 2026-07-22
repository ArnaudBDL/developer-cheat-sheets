# Go : Maps

## Create Maps

```go
configuration := map[string]string{
    "environment": "production",
    "port":        "8080",
}

users := make(map[int]string)
```

## Read and Write

```go
configuration["host"] = "localhost"
port := configuration["port"]
```

## Check Presence

```go
value, exists := configuration["environment"]
if exists {
    fmt.Println(value)
}
```

## Delete and Clear

```go
delete(configuration, "host")
clear(configuration)
```

## Iterate

```go
for key, value := range configuration {
    fmt.Println(key, value)
}
```

Map iteration order is not specified. Sort keys explicitly when deterministic output is required.
