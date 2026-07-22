# TypeScript : Classes

## Class Members

```typescript
class User {
  static readonly entityName = 'user';

  constructor(
    public readonly id: number,
    public name: string,
    private active = true,
  ) {}

  deactivate(): void {
    this.active = false;
  }
}
```

## Inheritance

```typescript
abstract class Entity {
  constructor(public readonly id: number) {}
  abstract serialize(): object;
}

class Article extends Entity {
  constructor(id: number, public title: string) {
    super(id);
  }

  override serialize(): object {
    return { id: this.id, title: this.title };
  }
}
```

## Implement an Interface

```typescript
interface Disposable {
  dispose(): void;
}

class Connection implements Disposable {
  dispose(): void {}
}
```

## ECMAScript Private Field

```typescript
class Counter {
  #value = 0;

  increment(): number {
    return ++this.#value;
  }
}
```
