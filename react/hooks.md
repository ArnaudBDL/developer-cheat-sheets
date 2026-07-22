# React : Hooks

## Common Hooks

```tsx
useState(initialState)
useReducer(reducer, initialState)
useContext(Context)
useRef(initialValue)
useEffect(setup, dependencies)
useMemo(calculate, dependencies)
useCallback(callback, dependencies)
useId()
```

## Effect with Cleanup

```tsx
useEffect(() => {
  const controller = new AbortController()
  loadUsers(controller.signal)

  return () => controller.abort()
}, [])
```

## Custom Hook

```tsx
export function useOnlineStatus() {
  const [online, setOnline] = useState(navigator.onLine)

  useEffect(() => {
    const update = () => setOnline(navigator.onLine)
    window.addEventListener('online', update)
    window.addEventListener('offline', update)
    return () => {
      window.removeEventListener('online', update)
      window.removeEventListener('offline', update)
    }
  }, [])

  return online
}
```

## Rules

```text
Call Hooks only at the top level of React components or custom Hooks. Keep components and Hooks pure. Use Effects to synchronize with external systems, not to derive ordinary rendering data.
```

