# Vue : Performance

## Lazy Loading

```typescript
const UserView = () => import('@/views/UserView.vue')
const HeavyPanel = defineAsyncComponent(() => import('./HeavyPanel.vue'))
```

## Stable Rendering

```vue
<li v-for="item in items" :key="item.id">
  {{ item.name }}
</li>

<section v-once>{{ staticContent }}</section>
<div v-memo="[item.id, item.updatedAt]">...</div>
```

## Reactive Cost

```typescript
const largeDataset = shallowRef(data)
largeDataset.value = nextData

const immutableConfiguration = readonly(configuration)
```

## Measure

```bash
npm run build
npm run preview

```

## Rules

```text
Profile before optimizing. Lazy-load routes and expensive components, keep props stable, virtualize very large lists, avoid unnecessary deep reactivity, and inspect the production bundle.
```

