# Angular : Templates

## Interpolation and Binding

```html
<h1>{{ title() }}</h1>
<img [src]="imageUrl()" [alt]="title()">
<button [disabled]="loading()" (click)="save()">Save</button>
<input [(ngModel)]="name">
```

## Built-In Control Flow

```html
@if (loading()) {
  <app-spinner />
} @else if (error()) {
  <p>{{ error() }}</p>
} @else {
  <ul>
    @for (user of users(); track user.id) {
      <li>{{ user.name }}</li>
    } @empty {
      <li>No users</li>
    }
  </ul>
}
```

## Switch and Deferred Content

```html
@switch (status()) {
  @case ('ready') { <app-ready /> }
  @case ('error') { <app-error /> }
  @default { <app-loading /> }
}

@defer (on viewport) {
  <app-heavy-panel />
} @placeholder {
  <p>Panel loading area</p>
}
```

