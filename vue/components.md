# Vue : Components

## Single-File Component

```vue
<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <button @click="count++">{{ count }}</button>
</template>

<style scoped>
button { font: inherit; }
</style>
```

## Use a Child Component

```vue
<script setup lang="ts">
import UserCard from './components/UserCard.vue'
</script>

<template>
  <UserCard />
</template>
```

## Slots

```vue
<template>
  <article>
    <header><slot name="header" /></header>
    <slot />
    <footer><slot name="footer" /></footer>
  </article>
</template>
```

