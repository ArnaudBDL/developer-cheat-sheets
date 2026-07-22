# React : Jsx

## Expressions

```tsx
export function Greeting({ name }: { name: string }) {
  const title = `Hello ${name}`

  return (
    <section className="greeting">
      <h1>{title}</h1>
      <img src="/avatar.png" alt={name} />
    </section>
  )
}
```

## Conditions

```tsx
{loading && <Spinner />}
{error ? <ErrorMessage error={error} /> : <Results items={items} />}
{status === 'ready' ? <Ready /> : null}
```

## Lists

```tsx
<ul>
  {items.map(item => (
    <li key={item.id}>{item.name}</li>
  ))}
</ul>
```

## Rules

```text
Close every tag. Return one parent element or a Fragment. Use className instead of class. Use camelCase DOM properties and event names. Place JavaScript expressions inside braces.
```

