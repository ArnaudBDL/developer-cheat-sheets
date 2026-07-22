# Node.js : Environment Variables

## Read Variables

```javascript
const environment = process.env.NODE_ENV ?? 'development';
const port = Number.parseInt(process.env.PORT ?? '3000', 10);
```

## Set Variables

```bash
NODE_ENV=production PORT=8080 node app.js
export NODE_ENV=production
node app.js
```

## Environment File

```dotenv
NODE_ENV=development
PORT=3000
DATABASE_URL=postgresql://localhost/application
```

```bash
node --env-file=.env app.js
```

## Validate Configuration

```javascript
function requiredEnvironmentVariable(name) {
  const value = process.env[name];
  if (!value) {
    throw new Error(`Missing environment variable: ${name}`);
  }

  return value;
}

const databaseUrl = requiredEnvironmentVariable('DATABASE_URL');
```

Do not commit environment files containing credentials or tokens.
