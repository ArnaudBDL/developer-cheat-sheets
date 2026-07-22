# React : State

## useState

```tsx
import { useState } from 'react'

const [count, setCount] = useState(0)
setCount(current => current + 1)
```

## Object State

```tsx
const [form, setForm] = useState({ email: '', active: true })

setForm(current => ({
  ...current,
  email: 'user@example.com'
}))
```

## Lift State Up

```tsx
function Accordion() {
  const [activePanel, setActivePanel] = useState<string | null>(null)

  return panels.map(panel => (
    <Panel
      key={panel.id}
      open={activePanel === panel.id}
      onOpen={() => setActivePanel(panel.id)}
    />
  ))
}
```

## Rules

```text
Do not mutate state directly. Use functional updates when the next value depends on the previous one. Avoid redundant or derivable state.
```

