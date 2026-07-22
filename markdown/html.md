# Markdown : HTML

## Inline HTML

```markdown
This line contains <kbd>Ctrl</kbd> + <kbd>C</kbd>.

<br>

<details>
<summary>Show details</summary>

Additional content.

</details>
```

## HTML Block

```html
<section>
  <h2>HTML section</h2>
  <p>HTML paragraph.</p>
</section>
```

## Compatibility and Security

- Raw HTML support varies by renderer.
- Platforms may sanitize or remove elements and attributes.
- Avoid scripts, inline event handlers and unsafe embeds.
- Prefer native Markdown when equivalent syntax exists.
- Test mixed Markdown and HTML on the actual target platform.
