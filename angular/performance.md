# Angular : Performance

## Lazy Loading and Deferrable Views

```typescript
{
  path: 'reports',
  loadComponent: () => import('./reports/reports').then(module => module.Reports),
}

@defer (on viewport) {
  <app-heavy-chart />
} @placeholder {
  <app-chart-skeleton />
}
```

## Efficient Templates

```html
@for (item of items(); track item.id) {
  <app-item [item]="item" />
}
```

## Build and Inspect

```bash
ng build
ng build --configuration production
ng serve --configuration production
```

## Rules

```text
Profile before optimizing. Use lazy routes and deferred views, track repeated items with stable identifiers, keep computed values out of template methods, prefer Signals or async bindings over manual subscriptions, and inspect production bundle budgets.
```

