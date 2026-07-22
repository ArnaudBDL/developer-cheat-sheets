# Vue : Events

## Declare and Emit

```vue
<script setup lang="ts">
const emit = defineEmits<{
  select: [identifier: number]
  close: []
}>()

function select(identifier: number) {
  emit('select', identifier)
}
</script>

<template>
  <button @click="select(42)">Select</button>
</template>
```

## Listen in Parent

```vue
<UserCard
  @select="handleSelect"
  @close="visible = false"
/>
```

## Event Modifiers

```vue
@click.stop="handler"
@click.prevent="handler"
@click.once="handler"
@keyup.enter="submit"
```

