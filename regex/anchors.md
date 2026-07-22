# Regular Expressions : Anchors

## Anchors

```regex
^     start of input or line in multiline mode
$     end of input or line in multiline mode
\b    word boundary
\B    non-word boundary
```

## Validation

```regex
^[A-Z]{3}-[0-9]{6}$
```

## Engine differences

```regex
\A    absolute start in Python and PCRE2
\z    absolute end in supporting engines
\Z    engine-specific end behavior
```
Multiline changes `^` and `$`, not dot behavior. Prefer a full-match API when available.

