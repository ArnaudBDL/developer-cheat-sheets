# React : Routing

## Install React Router

```bash
npm install react-router-dom
```

## Routes

```tsx
import { BrowserRouter, Route, Routes } from 'react-router-dom'

createRoot(document.getElementById('root')!).render(
  <BrowserRouter>
    <Routes>
      <Route path="/" element={<HomePage />} />
      <Route path="/users/:id" element={<UserPage />} />
      <Route path="*" element={<NotFoundPage />} />
    </Routes>
  </BrowserRouter>
)
```

## Navigation and Parameters

```tsx
import { Link, useNavigate, useParams } from 'react-router-dom'

const { id } = useParams()
const navigate = useNavigate()

<Link to="/">Home</Link>
<button onClick={() => navigate(`/users/${id}`)}>Open</button>
```

## Lazy Route Component

```tsx
const UserPage = lazy(() => import('./pages/UserPage'))

<Suspense fallback={<Loading />}>
  <UserPage />
</Suspense>
```

