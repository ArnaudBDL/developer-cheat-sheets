# Vue : Composables

## Composable

```typescript
import { onMounted, readonly, ref } from 'vue'

export function useUsers() {
  const users = ref<User[]>([])
  const loading = ref(false)
  const error = ref<unknown>(null)

  async function load() {
    loading.value = true
    error.value = null
    try {
      users.value = await fetchUsers()
    } catch (reason) {
      error.value = reason
    } finally {
      loading.value = false
    }
  }

  onMounted(load)

  return {
    users: readonly(users),
    loading: readonly(loading),
    error: readonly(error),
    load
  }
}
```

## Use a Composable

```vue
<script setup lang="ts">
import { useUsers } from '@/composables/useUsers'

const { users, loading, error, load } = useUsers()
</script>
```

## Conventions

```text
Use a `use` prefix. Accept reactive inputs when required. Return refs so destructuring keeps reactivity. Clean up listeners, timers and requests in lifecycle hooks or watcher cleanup.
```

