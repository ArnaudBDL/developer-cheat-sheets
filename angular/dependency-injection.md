# Angular : Dependency Injection

## Injection Token

```typescript
import { InjectionToken } from '@angular/core';

export interface ApiConfiguration {
  baseUrl: string;
}

export const API_CONFIGURATION = new InjectionToken<ApiConfiguration>('API_CONFIGURATION');
```

## Provide Values and Factories

```typescript
export const appConfig: ApplicationConfig = {
  providers: [
    { provide: API_CONFIGURATION, useValue: { baseUrl: '/api' } },
    {
      provide: LOGGER,
      useFactory: () => new Logger(inject(EnvironmentService).production()),
    },
  ],
};
```

## Inject Dependencies

```typescript
private readonly http = inject(HttpClient);
private readonly config = inject(API_CONFIGURATION);
private readonly optionalFeature = inject(FEATURE, { optional: true });
```

## Provider Forms

```text
useClass
useValue
useFactory
useExisting
multi: true
```

