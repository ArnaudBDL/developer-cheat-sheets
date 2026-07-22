# Regular Expressions : Characters

## Literal and escaped characters

```regex
hello
\. \* \+ \? \^ \$ \[ \] \{ \} \( \) \|
```

## Control characters

```text
\n newline
\r carriage return
\t tab
\f form feed
\\ literal backslash
```

## Code points

```regex
\x41
\u0041
\u{1F680}
```
Support varies by engine and Unicode mode. Escape regex syntax separately from the host language string syntax.

