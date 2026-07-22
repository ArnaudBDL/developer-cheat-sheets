# Markdown : Images

## Inline Image

```markdown
![Alternative text](images/architecture.png)
![Alternative text](images/architecture.png "Architecture diagram")
```

## Reference Image

```markdown
![Architecture diagram][architecture]

[architecture]: images/architecture.png "System architecture"
```

## Linked Image

```markdown
[![Project logo](images/logo.png)](https://example.com)
```

## Accessibility

- Describe the image purpose or information in alternative text.
- Use empty alternative text for a purely decorative image: `![](decoration.png)`.
- Do not repeat adjacent caption text unnecessarily.
- Keep important information available in text, not only inside the image.
