# Angular : Testing

## Component Test

```typescript
import { ComponentFixture, TestBed } from '@angular/core/testing';
import { CounterComponent } from './counter';

describe('CounterComponent', () => {
  let fixture: ComponentFixture<CounterComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      imports: [CounterComponent],
    }).compileComponents();

    fixture = TestBed.createComponent(CounterComponent);
    fixture.detectChanges();
  });

  it('increments the count', () => {
    fixture.nativeElement.querySelector('button').click();
    fixture.detectChanges();
    expect(fixture.nativeElement.textContent).toContain('1');
  });
});
```

## Service Test

```typescript
TestBed.configureTestingModule({
  providers: [UsersService, provideHttpClient(), provideHttpClientTesting()],
});

const service = TestBed.inject(UsersService);
const http = TestBed.inject(HttpTestingController);
```

## Routing Test

```typescript
const harness = await RouterTestingHarness.create();
await harness.navigateByUrl('/users/42', UserDetail);
expect(harness.routeNativeElement?.textContent).toContain('42');
```

## Run Tests

```bash
ng test
ng test --watch=false
ng test --code-coverage
```

