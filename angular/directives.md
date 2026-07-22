# Angular : Directives

## Attribute Directive

```typescript
import { Directive, ElementRef, HostListener, inject, input } from '@angular/core';

@Directive({
  selector: '[appHighlight]',
  standalone: true,
})
export class HighlightDirective {
  private readonly element = inject(ElementRef<HTMLElement>);
  readonly appHighlight = input('yellow');

  @HostListener('mouseenter')
  enter(): void {
    this.element.nativeElement.style.backgroundColor = this.appHighlight();
  }

  @HostListener('mouseleave')
  leave(): void {
    this.element.nativeElement.style.backgroundColor = '';
  }
}
```

## Use Directives

```html
<p [appHighlight]="'gold'">Highlighted text</p>
<div [class.active]="active()"></div>
<div [style.width.px]="width()"></div>
```

## Common Directives

```text
NgClass
NgStyle
NgModel
RouterLink
RouterLinkActive
RouterOutlet
```

