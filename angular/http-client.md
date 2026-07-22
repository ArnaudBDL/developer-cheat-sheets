# Angular : Http Client

## Configure HttpClient

```typescript
import { provideHttpClient, withInterceptors } from '@angular/common/http';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(withInterceptors([authenticationInterceptor])),
  ],
};
```

## HTTP Service

```typescript
@Injectable({ providedIn: 'root' })
export class UsersApi {
  private readonly http = inject(HttpClient);

  list(): Observable<User[]> {
    return this.http.get<User[]>('/api/users');
  }

  create(input: CreateUser): Observable<User> {
    return this.http.post<User>('/api/users', input);
  }
}
```

## Functional Interceptor

```typescript
export const authenticationInterceptor: HttpInterceptorFn = (request, next) => {
  const token = inject(SessionService).token();
  const authenticatedRequest = token
    ? request.clone({ setHeaders: { Authorization: `Bearer ${token}` } })
    : request;

  return next(authenticatedRequest);
};
```

## Reactive Resource

```typescript
readonly userId = input.required<string>();
readonly user = httpResource<User>(() => `/api/users/${this.userId()}`);
```

