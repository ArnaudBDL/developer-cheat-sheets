# JavaScript : Control Structures

## if and else

```javascript
if (score >= 80) {
  grade = 'A';
} else if (score >= 60) {
  grade = 'B';
} else {
  grade = 'C';
}
```

## switch

```javascript
switch (status) {
  case 'ready':
    start();
    break;
  case 'paused':
    resume();
    break;
  default:
    stop();
}
```

## Loops

```javascript
for (let index = 0; index < items.length; index += 1) {
  console.log(items[index]);
}

for (const item of items) {
  console.log(item);
}

for (const key in object) {
  if (Object.hasOwn(object, key)) {
    console.log(key, object[key]);
  }
}
```

## while

```javascript
while (condition) {
  process();
}

do {
  process();
} while (condition);
```

## Control

```javascript
break;
continue;
return value;
throw new Error('Failure');
```
