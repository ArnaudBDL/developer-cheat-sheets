# Angular : Services

## Root Service

```typescript
import { Injectable, signal } from '@angular/core';

@Injectable({ providedIn: 'root' })
export class SessionService {
  readonly user = signal<User | null>(null);

  signIn(user: User): void {
    this.user.set(user);
  }

  signOut(): void {
    this.user.set(null);
  }
}
```

## Inject a Service

```typescript
import { Component, inject } from '@angular/core';
import { SessionService } from './session.service';

@Component({
  selector: 'app-session',
  standalone: true,
  template: `{{ session.user()?.name ?? 'Anonymous' }}`,
})
export class SessionComponent {
  protected readonly session = inject(SessionService);
}
```

## Provider Scope

```text
providedIn: 'root'        Application singleton
component providers       Component subtree instance
route providers           Route-scoped instance
environment providers     Environment injector instance
```

