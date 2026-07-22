# Node.js : Events

## EventEmitter

```javascript
import { EventEmitter } from 'node:events';

const emitter = new EventEmitter();

emitter.on('ready', payload => {
  console.log(payload);
});

emitter.emit('ready', { status: 'ok' });
```

## One-Time Listener

```javascript
emitter.once('connected', () => {
  console.log('Connected once');
});
```

## Remove Listeners

```javascript
function listener(payload) {
  console.log(payload);
}

emitter.on('data', listener);
emitter.off('data', listener);
emitter.removeAllListeners('data');
```

## Error Events

```javascript
emitter.on('error', error => {
  console.error(error);
});
```

## Await an Event

```javascript
import { once } from 'node:events';

const [payload] = await once(emitter, 'ready');
```
