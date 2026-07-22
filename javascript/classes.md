# JavaScript : Classes

## Class Declaration

```javascript
class User {
  #name;

  constructor(id, name) {
    this.id = id;
    this.#name = name;
  }

  get name() {
    return this.#name;
  }

  rename(name) {
    this.#name = name;
  }
}
```

## Inheritance

```javascript
class Administrator extends User {
  constructor(id, name, permissions = []) {
    super(id, name);
    this.permissions = permissions;
  }

  can(permission) {
    return this.permissions.includes(permission);
  }
}
```

## Static Members

```javascript
class Identifier {
  static create() {
    return crypto.randomUUID();
  }
}
```

## Instance Checks

```javascript
const user = new User(42, 'Arnaud');
console.log(user instanceof User);
```

JavaScript classes use the language's prototype-based object model.
