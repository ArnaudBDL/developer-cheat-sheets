# React : Testing

## Install

```bash
npm install --save-dev vitest jsdom @testing-library/react @testing-library/jest-dom @testing-library/user-event
```

## Component Test

```tsx
import { render, screen } from '@testing-library/react'
import userEvent from '@testing-library/user-event'
import { expect, it } from 'vitest'
import Counter from './Counter'

it('increments the count', async () => {
  const user = userEvent.setup()
  render(<Counter />)

  await user.click(screen.getByRole('button', { name: /increment/i }))
  expect(screen.getByText('1')).toBeInTheDocument()
})
```

## Run

```bash
npx vitest
npx vitest run
npx vitest run --coverage
```

## Rule

```text
Prefer queries that reflect accessible user interactions, such as role, label and visible text. Test behavior rather than internal implementation details.
```

