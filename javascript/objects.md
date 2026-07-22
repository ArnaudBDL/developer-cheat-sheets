# JavaScript : Objects

## Create an Object

```javascript
const user = {
  id: 42,
  name: 'Arnaud',
  active: true,
  displayName() {
    return this.name;
  },
};
```

## Access and Update

```javascript
const name = user.name;
const dynamic = user[propertyName];
user.active = false;
delete user.active;
```

## Copy and Merge

```javascript
const copy = { ...user };
const configured = { ...defaults, ...options };
const deepCopy = structuredClone(source);
```

## Keys and Values

```javascript
Object.keys(user);
Object.values(user);
Object.entries(user);
Object.hasOwn(user, 'id');
```

## Destructuring

```javascript
const { id, name, active = true } = user;
```

## Freeze and Seal

```javascript
Object.freeze(configuration);
Object.seal(state);
```
