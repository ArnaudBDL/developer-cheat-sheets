# Angular : Signals

## Signal State

```typescript
import { computed, effect, signal } from '@angular/core';

readonly count = signal(0);
readonly doubled = computed(() => this.count() * 2);

increment(): void {
  this.count.update(value => value + 1);
}

reset(): void {
  this.count.set(0);
}
```

## Effect Cleanup

```typescript
private readonly loggerEffect = effect(onCleanup => {
  const timerId = window.setTimeout(() => {
    console.log(this.count());
  }, 250);

  onCleanup(() => window.clearTimeout(timerId));
});
```

## Signal Inputs and Queries

```typescript
readonly user = input.required<User>();
readonly selected = output<number>();
readonly panel = viewChild.required<ElementRef>('panel');
readonly items = contentChildren(ItemComponent);
```

## Interop

```typescript
toSignal(observable$, { initialValue: [] })
toObservable(searchSignal)
takeUntilDestroyed()
```

