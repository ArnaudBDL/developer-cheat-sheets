# Angular : Rxjs

## Observable Pipeline

```typescript
readonly users$ = this.search.valueChanges.pipe(
  debounceTime(300),
  distinctUntilChanged(),
  switchMap(query => this.usersService.search(query)),
  catchError(error => {
    console.error(error);
    return of([]);
  }),
  shareReplay({ bufferSize: 1, refCount: true }),
);
```

## Common Creation Functions

```typescript
of(value)
from(iterable)
interval(milliseconds)
timer(delay)
combineLatest(sources)
forkJoin(sources)
merge(sources)
EMPTY
throwError(factory)
```

## Common Operators

```text
map
filter
tap
switchMap
concatMap
mergeMap
exhaustMap
catchError
retry
finalize
take
takeUntil
shareReplay
```

## Subscription Lifecycle

```typescript
private readonly destroyRef = inject(DestroyRef);

stream$.pipe(
  takeUntilDestroyed(this.destroyRef),
).subscribe(value => console.log(value));
```

