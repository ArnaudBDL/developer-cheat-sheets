# Node.js : Buffers

## Create Buffers

```javascript
import { Buffer } from 'node:buffer';

const empty = Buffer.alloc(16);
const bytes = Buffer.from([0x48, 0x69]);
const text = Buffer.from('Hello', 'utf8');
```

## Convert

```javascript
const text = buffer.toString('utf8');
const hex = buffer.toString('hex');
const base64 = buffer.toString('base64');
const restored = Buffer.from(base64, 'base64');
```

## Read and Write

```javascript
const buffer = Buffer.alloc(8);
buffer.writeUInt32BE(42, 0);
buffer.writeDoubleBE(19.99, 0);

const value = buffer.readUInt32BE(0);
```

## Combine and Compare

```javascript
const combined = Buffer.concat([first, second]);
const equal = first.equals(second);
const result = Buffer.compare(first, second);
```

## Slicing

```javascript
const copy = Buffer.from(buffer.subarray(0, 4));
```
