# Angular : Routing

## Routes

```typescript
import { Routes } from '@angular/router';

export const routes: Routes = [
  {
    path: '',
    loadComponent: () => import('./home/home').then(module => module.Home),
  },
  {
    path: 'users/:id',
    loadComponent: () => import('./users/user-detail').then(module => module.UserDetail),
  },
  { path: '**', redirectTo: '' },
];
```

## Configure Router

```typescript
import { ApplicationConfig } from '@angular/core';
import { provideRouter, withComponentInputBinding } from '@angular/router';
import { routes } from './app.routes';

export const appConfig: ApplicationConfig = {
  providers: [provideRouter(routes, withComponentInputBinding())],
};
```

## Navigation

```html
<a routerLink="/">Home</a>
<a [routerLink]="['/users', user.id]" routerLinkActive="active">User</a>
<router-outlet />
```

## Programmatic Navigation

```typescript
private readonly router = inject(Router);
private readonly route = inject(ActivatedRoute);

this.router.navigate(['/users', id]);
const id = this.route.snapshot.paramMap.get('id');
```

