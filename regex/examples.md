# Regular Expressions : Examples

## Identifier

```regex
^[A-Za-z_][A-Za-z0-9_]*$
```

## Date shape

```regex
^[0-9]{4}-[0-9]{2}-[0-9]{2}$
```
This checks shape, not calendar validity.

## IPv4 shape

```regex
^(?:[0-9]{1,3}\.){3}[0-9]{1,3}$
```
This does not enforce octets from 0 through 255.

## Guidance

Use dedicated parsers for URLs, email addresses, IP addresses and dates when standards compliance matters. Pair regex validation with input-length limits and semantic validation.

