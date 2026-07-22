# Vue : Quick References

## Component

```vue
<script setup lang="ts">
import { computed, ref } from "vue";
const count = ref(0);
const doubled = computed(() => count.value * 2);
</script>

<template>
  <button @click="count++">{{ doubled }}</button>
</template>
```

## CLI

```bash
npm create vue@latest
npm install
npm run dev
npm run build
npm run test:unit
```
