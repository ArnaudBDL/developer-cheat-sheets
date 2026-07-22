# Vue : Testing

## Install

```bash
npm install --save-dev vitest @vue/test-utils jsdom
```

## Component Test

```typescript
import { mount } from '@vue/test-utils'
import { describe, expect, it } from 'vitest'
import CounterButton from '../CounterButton.vue'

describe('CounterButton', () => {
  it('increments the counter', async () => {
    const wrapper = mount(CounterButton)
    await wrapper.get('button').trigger('click')
    expect(wrapper.text()).toContain('1')
  })
})
```

## Composables

```typescript
import { expect, it } from 'vitest'
import { useCounter } from '../useCounter'

it('increments', () => {
  const { count, increment } = useCounter()
  increment()
  expect(count.value).toBe(1)
})
```

## Run

```bash
npm run test:unit
npx vitest run
npx vitest --coverage
```

