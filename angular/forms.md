# Angular : Forms

## Reactive Form

```typescript
import { FormControl, FormGroup, ReactiveFormsModule, Validators } from '@angular/forms';

readonly form = new FormGroup({
  email: new FormControl('', {
    nonNullable: true,
    validators: [Validators.required, Validators.email],
  }),
  active: new FormControl(true, { nonNullable: true }),
});

submit(): void {
  if (this.form.invalid) {
    this.form.markAllAsTouched();
    return;
  }

  console.log(this.form.getRawValue());
}
```

## Reactive Form Template

```html
<form [formGroup]="form" (ngSubmit)="submit()">
  <input type="email" formControlName="email">
  @if (form.controls.email.touched && form.controls.email.invalid) {
    <p>Invalid email</p>
  }
  <input type="checkbox" formControlName="active">
  <button type="submit" [disabled]="form.pending">Save</button>
</form>
```

## Template-Driven Form

```html
<form #form="ngForm" (ngSubmit)="save(form.value)">
  <input name="email" type="email" [(ngModel)]="email" required>
  <button type="submit" [disabled]="form.invalid">Save</button>
</form>
```

