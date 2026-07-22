# Vue : Props

## Typed Props

```vue
<script setup lang="ts">
interface Props {
  title: string
  active?: boolean
  count?: number
}

const props = withDefaults(defineProps<Props>(), {
  active: true,
  count: 0
})
</script>
```

## Use Props

```vue
<template>
  <h2>{{ props.title }}</h2>
  <p v-if="props.active">{{ props.count }}</p>
</template>
```

## Rule

```text
Props flow from parent to child and are read-only in the child. Emit an event instead of mutating a prop.
```

