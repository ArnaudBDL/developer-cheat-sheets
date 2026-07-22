# Vue : Reactivity

## ref and reactive

```typescript
import { computed, reactive, ref, watch } from 'vue'

const count = ref(0)
const user = reactive({ name: 'Arnaud', active: true })
const doubled = computed(() => count.value * 2)

watch(count, (current, previous) => {
  console.log(previous, current)
})
```

## Watch Effect

```typescript
const stop = watchEffect(onCleanup => {
  const controller = new AbortController()
  loadData(query.value, controller.signal)
  onCleanup(() => controller.abort())
})

stop()
```

## Utilities

```typescript
isRef(value)
unref(value)
toRef(object, 'property')
toRefs(object)
readonly(state)
shallowRef(value)
triggerRef(reference)
```

