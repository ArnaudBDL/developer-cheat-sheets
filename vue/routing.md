# Vue : Routing

## Router Configuration

```typescript
import { createRouter, createWebHistory } from 'vue-router'

export default createRouter({
  history: createWebHistory(),
  routes: [
    { path: '/', name: 'home', component: () => import('@/views/HomeView.vue') },
    { path: '/users/:id', name: 'user', component: () => import('@/views/UserView.vue'), props: true },
    { path: '/:pathMatch(.*)*', name: 'not-found', component: () => import('@/views/NotFoundView.vue') }
  ]
})
```

## Composition API

```typescript
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()

await router.push({ name: 'user', params: { id: 42 } })
watch(() => route.params.id, loadUser)
```

## Template

```vue
<RouterLink :to="{ name: 'home' }">Home</RouterLink>
<RouterView />
```

