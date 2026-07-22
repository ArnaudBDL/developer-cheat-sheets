# Vue : Application

## Application Entry

```typescript
import { createApp } from 'vue'
import App from './App.vue'
import './assets/main.css'

const app = createApp(App)
app.mount('#app')
```

## Register Plugins

```typescript
import { createPinia } from 'pinia'
import router from './router'

createApp(App)
  .use(createPinia())
  .use(router)
  .mount('#app')
```

## Application Configuration

```typescript
app.config.errorHandler = (error, instance, info) => {
  console.error(error, info)
}

app.provide('apiBaseUrl', '/api')
```

