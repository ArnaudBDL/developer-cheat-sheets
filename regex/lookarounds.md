# Regular Expressions : Lookarounds

## Lookahead

```regex
[0-9]+(?=px)
[0-9]+(?!px)
```

## Lookbehind

```regex
(?<=\$)[0-9]+
(?<!\$)[0-9]+
```

## Rules

Lookarounds test context without consuming it. Lookbehind support and length restrictions vary. Go's standard engine does not support lookarounds. Benchmark complex assertions on adversarial input.

