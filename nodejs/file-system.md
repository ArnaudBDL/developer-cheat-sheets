# Node.js : File System

## Promise API

```javascript
import fs from 'node:fs/promises';

const content = await fs.readFile('data.json', 'utf8');
const data = JSON.parse(content);

await fs.writeFile('output.json', JSON.stringify(data, null, 2));
```

## Directories

```javascript
await fs.mkdir('output/reports', { recursive: true });
const entries = await fs.readdir('output', { withFileTypes: true });
await fs.rm('output', { recursive: true, force: true });
```

## File Metadata

```javascript
const stats = await fs.stat('file.txt');
console.log(stats.isFile());
console.log(stats.size);
console.log(stats.mtime);
```

## Paths and URLs

```javascript
import path from 'node:path';
import { fileURLToPath } from 'node:url';

const filename = fileURLToPath(import.meta.url);
const directory = path.dirname(filename);
const target = path.join(directory, 'data', 'file.json');
```

## Watch Files

```javascript
const watcher = fs.watch('config');
for await (const event of watcher) {
  console.log(event.eventType, event.filename);
}
```
