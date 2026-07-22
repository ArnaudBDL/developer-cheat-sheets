# Vue : Composition Api

## Script Setup

```vue
<script setup lang="ts">
import { computed, onMounted, ref } from 'vue'

const count = ref(0)
const doubled = computed(() => count.value * 2)

onMounted(() => {
  console.log('Mounted')
})
</script>
```

## Lifecycle Hooks

```typescript
onBeforeMount(callback)
onMounted(callback)
onBeforeUpdate(callback)
onUpdated(callback)
onBeforeUnmount(callback)
onUnmounted(callback)
onErrorCaptured(callback)
```

## Provide and Inject

```typescript
const key = Symbol('configuration')
provide(key, configuration)
const configuration = inject(key)
```

