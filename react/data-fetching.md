# React : Data Fetching

## Fetch in an Effect

```tsx
function Users() {
  const [users, setUsers] = useState<User[]>([])
  const [error, setError] = useState<unknown>(null)
  const [loading, setLoading] = useState(true)

  useEffect(() => {
    const controller = new AbortController()

    async function load() {
      try {
        const response = await fetch('/api/users', { signal: controller.signal })
        if (!response.ok) throw new Error(`HTTP ${response.status}`)
        setUsers(await response.json())
      } catch (reason) {
        if (!controller.signal.aborted) setError(reason)
      } finally {
        if (!controller.signal.aborted) setLoading(false)
      }
    }

    load()
    return () => controller.abort()
  }, [])

  return <UserList users={users} loading={loading} error={error} />
}
```

## Rules

```text
Handle non-successful HTTP status values, cancellation, loading and error states. Prefer framework or router data-loading facilities when the application architecture already provides them.
```

