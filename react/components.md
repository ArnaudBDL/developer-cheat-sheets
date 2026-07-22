# React : Components

## Function Component

```tsx
type UserCardProps = {
  name: string
  active: boolean
}

export function UserCard({ name, active }: UserCardProps) {
  return (
    <article>
      <h2>{name}</h2>
      <p>{active ? 'Active' : 'Inactive'}</p>
    </article>
  )
}
```

## Composition

```tsx
export function Page() {
  return (
    <Layout>
      <Header />
      <main><UserList /></main>
    </Layout>
  )
}
```

## Children

```tsx
type PanelProps = {
  title: string
  children: React.ReactNode
}

export function Panel({ title, children }: PanelProps) {
  return <section><h2>{title}</h2>{children}</section>
}
```

