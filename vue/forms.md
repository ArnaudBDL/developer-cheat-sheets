# Vue : Forms

## v-model

```vue
<script setup lang="ts">
import { reactive } from 'vue'

const form = reactive({
  email: '',
  role: 'viewer',
  active: true
})
</script>

<template>
  <form @submit.prevent="submit">
    <input v-model.trim="form.email" type="email" required>
    <select v-model="form.role">
      <option value="viewer">Viewer</option>
      <option value="editor">Editor</option>
    </select>
    <input v-model="form.active" type="checkbox">
    <button type="submit">Save</button>
  </form>
</template>
```

## Modifiers

```vue
v-model.trim="name"
v-model.number="quantity"
v-model.lazy="value"
```

## Component Model

```vue
<script setup lang="ts">
const model = defineModel<string>({ required: true })
</script>

<template>
  <input v-model="model">
</template>
```

