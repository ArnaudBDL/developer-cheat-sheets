# Angular : Components

## Standalone Component

```typescript
import { ChangeDetectionStrategy, Component, input, output } from '@angular/core';

@Component({
  selector: 'app-user-card',
  standalone: true,
  templateUrl: './user-card.html',
  styleUrl: './user-card.scss',
  changeDetection: ChangeDetectionStrategy.OnPush,
})
export class UserCard {
  readonly user = input.required<User>();
  readonly selected = output<number>();

  select(): void {
    this.selected.emit(this.user().id);
  }
}
```

## Use a Component

```typescript
import { Component } from '@angular/core';
import { UserCard } from './user-card';

@Component({
  selector: 'app-user-list',
  standalone: true,
  imports: [UserCard],
  template: `
    <app-user-card
      [user]="user"
      (selected)="selectUser($event)"
    />
  `,
})
export class UserList {
  user: User = { id: 42, name: 'Arnaud' };

  selectUser(id: number): void {
    console.log(id);
  }
}
```

## Lifecycle

```typescript
ngOnInit(): void {}
ngOnChanges(changes: SimpleChanges): void {}
ngAfterViewInit(): void {}
ngOnDestroy(): void {}
```

