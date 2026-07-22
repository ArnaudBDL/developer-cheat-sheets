# Express : Application

## Application Factory

```javascript
// src/app.js
import express from 'express';

export function createApplication() {
  const app = express();

  app.disable('x-powered-by');
  app.use(express.json({ limit: '1mb' }));
  app.use(express.urlencoded({ extended: false, limit: '1mb' }));

  app.get('/health', (request, response) => {
    response.status(200).json({ status: 'ok' });
  });

  return app;
}
```

## HTTP Server

```javascript
// src/server.js
import { createApplication } from './app.js';

const port = Number.parseInt(process.env.PORT ?? '3000', 10);
const app = createApplication();

const server = app.listen(port, () => {
  console.log(`Server listening on port ${port}`);
});

function shutdown(signal) {
  console.log(`${signal} received`);
  server.close(error => {
    if (error) {
      console.error(error);
      process.exitCode = 1;
    }
  });
}

process.on('SIGTERM', () => shutdown('SIGTERM'));
process.on('SIGINT', () => shutdown('SIGINT'));
```

## Application Settings

```javascript
app.set('trust proxy', 1);
app.set('json spaces', process.env.NODE_ENV === 'development' ? 2 : 0);
app.get('env');
app.get('trust proxy');
```
