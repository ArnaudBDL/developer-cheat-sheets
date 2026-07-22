# React : Forms

## Controlled Form

```tsx
function UserForm() {
  const [email, setEmail] = useState('')
  const [active, setActive] = useState(true)

  function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault()
    saveUser({ email, active })
  }

  return (
    <form onSubmit={handleSubmit}>
      <input type="email" value={email} onChange={event => setEmail(event.target.value)} required />
      <input type="checkbox" checked={active} onChange={event => setActive(event.target.checked)} />
      <button type="submit">Save</button>
    </form>
  )
}
```

## Uncontrolled Input

```tsx
const inputRef = useRef<HTMLInputElement>(null)
const value = inputRef.current?.value

return <input ref={inputRef} defaultValue="Initial" />
```

## Rules

```text
Use value or checked with onChange for controlled fields. Prevent the native submit when handling submission in JavaScript. Validate again at the trusted server boundary.
```

