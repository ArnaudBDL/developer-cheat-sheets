# React : Context

## Create Context

```tsx
import { createContext, useContext } from 'react'

type Theme = 'light' | 'dark'
const ThemeContext = createContext<Theme>('light')

export function useTheme() {
  return useContext(ThemeContext)
}
```

## Provide and Read

```tsx
function App() {
  return (
    <ThemeContext value="dark">
      <Page />
    </ThemeContext>
  )
}

function Button() {
  const theme = useTheme()
  return <button className={`button-${theme}`}>Save</button>
}
```

## Rule

```text
Use Context for data needed by distant descendants. Keep frequently changing values focused and memoize compound provider values when necessary.
```

