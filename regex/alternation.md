# Regular Expressions : Alternation

## Choice

```regex
cat|dog|bird
^(?:GET|POST|PUT|PATCH|DELETE)$
```

## Shared structure

```regex
https?://
```
This factors the shared prefix of `http://|https://`.

## Rules

Alternation has low precedence, so group it when anchors or quantifiers apply to the entire choice. Order can matter in leftmost-first engines. Escape user-controlled alternatives.

