# Markdown : Links

## Inline Links

```markdown
[Descriptive link text](https://example.com)
[Documentation](https://example.com/docs "Optional title")
```

## Reference Links

```markdown
Read the [project documentation][docs].

[docs]: https://example.com/docs "Project documentation"
```

## Relative Links

```markdown
[Installation guide](docs/installation.md)
[Parent document](../README.md)
[Section](#configuration)
```

Use meaningful link text rather than generic labels such as “here”. Verify relative paths and generated heading anchors on the target renderer.
