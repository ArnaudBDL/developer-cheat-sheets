# React : Props

## Typed Props

```tsx
type ButtonProps = {
  label: string
  disabled?: boolean
  onPress: () => void
}

export function Button({ label, disabled = false, onPress }: ButtonProps) {
  return <button disabled={disabled} onClick={onPress}>{label}</button>
}
```

## Object and Callback Props

```tsx
<UserCard
  user={user}
  selected={selectedUserId === user.id}
  onSelect={() => setSelectedUserId(user.id)}
/>
```

## Rule

```text
Props are read-only inputs. A child requests changes through callbacks rather than mutating parent data.
```

