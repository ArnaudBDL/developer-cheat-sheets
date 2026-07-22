# Regular Expressions : Character Classes

## Classes

```regex
[abc]       one enclosed character
[^abc]      one character not enclosed
[a-z]       ASCII lowercase range
[0-9_-]     digit, underscore or hyphen
```

## Shorthand classes

```regex
\d \D \w \W \s \S
```
In JavaScript, `\\d` is equivalent to `[0-9]` and `\\w` covers basic Latin letters, digits and underscore.

## Unicode properties

```regex
\p{L}+
\p{N}+
\p{Script=Greek}+
```
Requires compatible engine support and Unicode mode. Never use `[A-z]` as a letter range.

