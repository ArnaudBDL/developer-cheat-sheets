# Regular Expressions : Quantifiers

## Greedy forms

```regex
*       zero or more
+       one or more
?       zero or one
{3}     exactly three
{3,}    three or more
{3,5}   three through five
```

## Lazy forms

```regex
*? +? ?? {3,5}?
```
Lazy quantifiers prefer the shortest match that permits the complete pattern to succeed.

## Safety

Quantifiers apply to the preceding atom or group. Avoid nested ambiguous quantifiers on untrusted input. Use explicit bounds where possible. Possessive quantifiers are engine-specific.

