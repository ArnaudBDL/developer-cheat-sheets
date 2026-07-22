# Express : Testing

## Install Test Tools

```bash
npm install --save-dev supertest
```

## Application Test

```javascript
import assert from 'node:assert/strict';
import test from 'node:test';
import request from 'supertest';
import { createApplication } from '../src/app.js';

test('GET /health returns the application status', async () => {
  const application = createApplication();
  const response = await request(application)
    .get('/health')
    .expect('content-type', /json/)
    .expect(200);

  assert.deepEqual(response.body, { status: 'ok' });
});
```

## Validation Test

```javascript
test('POST /api/articles rejects invalid input', async () => {
  const application = createApplication();

  await request(application)
    .post('/api/articles')
    .send({ title: '' })
    .expect(422);
});
```

## Run Tests

```bash
node --test
node --test test/*.test.js
node --test --test-name-pattern='health'
```

Export the Express application separately from `listen()` so tests can exercise it without opening a network port.
