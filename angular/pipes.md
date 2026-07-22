# Angular : Pipes

## Built-In Pipes

```html
{{ createdAt() | date:'dd/MM/yyyy HH:mm' }}
{{ amount() | currency:'EUR':'symbol':'1.2-2':'fr-FR' }}
{{ ratio() | percent:'1.0-2' }}
{{ name() | uppercase }}
{{ data() | json }}
{{ stream$ | async }}
```

## Custom Pipe

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'truncate',
  standalone: true,
  pure: true,
})
export class TruncatePipe implements PipeTransform {
  transform(value: string, length = 80): string {
    return value.length <= length ? value : `${value.slice(0, length)}…`;
  }
}
```

## Use a Custom Pipe

```html
<p>{{ description() | truncate:120 }}</p>
```

