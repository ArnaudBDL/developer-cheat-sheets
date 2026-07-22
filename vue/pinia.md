# Vue : Pinia

## Setup Store

```typescript
import { computed, ref } from 'vue'
import { defineStore } from 'pinia'

export const useCartStore = defineStore('cart', () => {
  const items = ref<CartItem[]>([])
  const totalItems = computed(() => items.value.length)

  function add(item: CartItem) {
    items.value.push(item)
  }

  function clear() {
    items.value = []
  }

  return { items, totalItems, add, clear }
})
```

## Use Store

```vue
<script setup lang="ts">
import { storeToRefs } from 'pinia'
import { useCartStore } from '@/stores/cart'

const cart = useCartStore()
const { items, totalItems } = storeToRefs(cart)
</script>
```

## Reset and Subscribe

```typescript
cart.$reset()
cart.$patch({ items: [] })
const unsubscribe = cart.$subscribe((mutation, state) => {
  console.log(mutation.type, state)
})
unsubscribe()
```

