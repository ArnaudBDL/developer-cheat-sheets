# Markdown : Code

## Inline Code

```markdown
Run `npm install` before starting the application.
Use `` `code` `` when the content contains a backtick.
```

## Fenced Code Block

````markdown
```typescript
function greet(name: string): string {
  return `Hello ${name}`
}
```
````

## Indented Code Block

```markdown
    const enabled = true
    console.log(enabled)
```

Use a language identifier on fenced code blocks when syntax highlighting is supported. Keep code complete enough to understand and copy safely.
