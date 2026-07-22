# Angular : Quick References

## CLI

```bash
ng new my-app
ng serve
ng generate component feature/name
ng generate service core/name
ng build
ng test
```

## Signals

```typescript
readonly count = signal(0);
readonly doubled = computed(() => this.count() * 2);

increment(): void {
  this.count.update(value => value + 1);
}
```

## HTTP

```typescript
readonly users = toSignal(
  this.http.get<User[]>("/api/users"),
  { initialValue: [] }
);
```

## Template

```html
@if (user(); as user) {
  <h2>{{ user.name }}</h2>
}

@for (item of items(); track item.id) {
  <div>{{ item.label }}</div>
}
```
