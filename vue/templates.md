# Vue : Templates

## Interpolation and Binding

```vue
<template>
  <h1>{{ title }}</h1>
  <img :src="imageUrl" :alt="title">
  <button :disabled="loading" @click="submit">Save</button>
</template>
```

## Conditionals and Lists

```vue
<template>
  <p v-if="loading">Loading...</p>
  <p v-else-if="error">{{ error }}</p>
  <ul v-else>
    <li v-for="item in items" :key="item.id">
      {{ item.name }}
    </li>
  </ul>
</template>
```

## Directives

```text
v-bind:href="url"       :href="url"
v-on:click="handler"    @click="handler"
v-model="value"
v-if / v-else-if / v-else
v-show="visible"
v-for="item in items"
v-html="trustedHtml"
```

