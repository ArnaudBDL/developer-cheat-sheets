# React : Quick References

## Component

```tsx
type Props = { title: string };

export function Card({ title }: Props) {
  return <article>{title}</article>;
}
```

## State and effect

```tsx
const [count, setCount] = useState(0);

useEffect(() => {
  document.title = String(count);
}, [count]);
```

## Memoization

```tsx
const filtered = useMemo(
  () => items.filter(item => item.active),
  [items]
);
const handleClick = useCallback(() => setOpen(true), []);
```
