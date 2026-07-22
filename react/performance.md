# React : Performance

## Memoization

```tsx
const filteredItems = useMemo(
  () => filterItems(items, query),
  [items, query]
)

const handleSelect = useCallback(
  (id: number) => setSelectedId(id),
  []
)

const ItemList = memo(function ItemList({ items }: Props) {
  return items.map(item => <Item key={item.id} item={item} />)
})
```

## Code Splitting

```tsx
const ReportsPage = lazy(() => import('./pages/ReportsPage'))

<Suspense fallback={<Loading />}>
  <ReportsPage />
</Suspense>
```

## Measure

```bash
npm run build
npm run preview
```

## Rules

```text
Profile before optimizing. Keep state local, avoid unnecessary Effects, preserve stable keys, virtualize very large lists, split expensive routes, and use memoization only when it removes measured work.
```

