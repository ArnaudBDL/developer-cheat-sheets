# TypeScript : Decorators

## Class Decorator

```typescript
function Registered<T extends abstract new (...args: any[]) => object>(target: T): T {
  registry.add(target.name);
  return target;
}

@Registered
class ApplicationService {}
```

## Method Decorator

```typescript
function Logged<This, Args extends unknown[], Return>(
  originalMethod: (this: This, ...args: Args) => Return,
  context: ClassMethodDecoratorContext<This, (this: This, ...args: Args) => Return>,
) {
  return function (this: This, ...args: Args): Return {
    console.log(`Calling ${String(context.name)}`);
    return originalMethod.call(this, ...args);
  };
}

class Service {
  @Logged
  execute(value: string): string {
    return value;
  }
}
```

## Decorator Factory

```typescript
function Tagged(tag: string) {
  return function <T extends abstract new (...args: any[]) => object>(target: T): T {
    Reflect.defineProperty(target, 'tag', { value: tag });
    return target;
  };
}

@Tagged('service')
class UserService {}
```

Decorators execute at class definition time. Keep decorator behavior explicit and avoid hidden side effects.
