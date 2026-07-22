# Node.js : Streams

## Pipe Files

```javascript
import fs from 'node:fs';
import { pipeline } from 'node:stream/promises';

await pipeline(
  fs.createReadStream('input.txt'),
  fs.createWriteStream('output.txt'),
);
```

## Transform Stream

```javascript
import { Transform } from 'node:stream';

const uppercase = new Transform({
  transform(chunk, encoding, callback) {
    callback(null, chunk.toString().toUpperCase());
  },
});
```

## Async Iteration

```javascript
for await (const chunk of readable) {
  console.log(chunk);
}
```

## Readable from Data

```javascript
import { Readable } from 'node:stream';

const readable = Readable.from(['one
', 'two
']);
readable.pipe(process.stdout);
```

## Backpressure

Use `pipeline()` or respect the Boolean returned by `writable.write()` and wait for the `drain` event before continuing writes.
