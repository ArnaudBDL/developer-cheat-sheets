# React : Installation

## Create with Vite

```bash
npm create vite@latest application -- --template react-ts
cd application
npm install
npm run dev
```

## Common Commands

```bash
npm run dev
npm run build
npm run preview
npm run lint
```

## Application Entry

```tsx
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import App from './App'
import './index.css'

createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <App />
  </StrictMode>
)
```

